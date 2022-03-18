public function repwdPut(){
        $xhprof_enable = false;
//        if(mt_rand(1,10)==1){ //这里设置监控的比例
        if(true){ //这里设置监控的比例必现
            xhprof_enable();
            $xhprof_enable = true;
        }

        /* 这里写上你要监控的函数
        $uid = $this->_params['uid'];
        $pwd = $this->_params['pwd'];
        $result = $this->_iam->repwd($uid,$pwd);
	结束*/

        if($xhprof_enable ){
            $xhprof_data = xhprof_disable();
            //$XHPROF_ROOT = realpath(dirname(__FILE__) .'/..');
            $XHPROF_ROOT = '/var/www/xhprof';
             include_once $XHPROF_ROOT . "/xhprof_lib/utils/xhprof_lib.php";
             include_once $XHPROF_ROOT . "/xhprof_lib/utils/xhprof_runs.php";
             // 使用默认设置保存此探查器运行的原始数据
	     // iXHProfRuns的实现。
             $xhprof_runs = new XHProfRuns_Default();
             // 将运行保存在名称空间“xhprof_foo”下
             $run_id = $xhprof_runs->save_run($xhprof_data, "xhprof_foo");
        }
	
	//接口返回值
        $this->_helper->json($result);
    }