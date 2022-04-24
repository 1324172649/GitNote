Javascript：
/**
 * 可用常数：
 * Available constants:
 * 他们要给一个值为空的字段分配一个类型。
 *   They are to assign a type to a field with a value null.
 * sdc。空布尔值，sdc。空字符，sdc。空字节，sdc。空_SHORT，sdc。NULL_整数，sdc。乌龙，
 *   sdc.NULL_BOOLEAN, sdc.NULL_CHAR, sdc.NULL_BYTE, sdc.NULL_SHORT, sdc.NULL_INTEGER, sdc.NULL_LONG,
 * sdc。空浮点数，sdc。空双，sdc。空日期，sdc。空的日期时间，sdc。空时间，sdc。零位小数，
 *   sdc.NULL_FLOAT, sdc.NULL_DOUBLE, sdc.NULL_DATE, sdc.NULL_DATETIME, sdc.NULL_TIME, sdc.NULL_DECIMAL,
 * sdc。空字节数组，sdc。空字符串，sdc。空列表，sdc。空映射
 *   sdc.NULL_BYTE_ARRAY, sdc.NULL_STRING, sdc.NULL_LIST, sdc.NULL_MAP
 *
 * 可用对象：
 * Available Objects:
 *
 * sdc。记录：要处理的记录数组，具体取决于JavaScript处理器
 *  sdc.records: an array of records to process, depending on the JavaScript processor
 * 处理模式它可能有一条记录或批次中的所有记录。
 *           processing mode it may have 1 record or all the records in the batch.
 *
 * sdc。状态：在调用该脚本之间保留的一个dict。
 *  sdc.state: a dict that is preserved between invocations of this script.
 * 用于缓存数据位，例如计数器。
 *        Useful for caching bits of data e.g. counters.
 *
 * sdc。日志<日志级别>（msg，obj…）：使用而不是打印将日志消息发送到log4j日志，而不是stdout。
 *  sdc.log.<loglevel>(msg, obj...): use instead of print to send log messages to the log4j log instead of stdout.
 * loglevel是任何log4j级别：例如信息、错误、警告、跟踪。
 *                               loglevel is any log4j level: e.g. info, error, warn, trace.
 *
 * sdc。输出写入（记录）：将记录写入处理器输出
 *  sdc.output.write(record): writes a record to processor output
 *
 * sdc。错误写入（记录、消息）：向错误发送记录
 *  sdc.error.write(record, message): sends a record to error
 *
 * sdc。getFieldNull（记录“字段路径”）：接收上面定义的常量
 *  sdc.getFieldNull(Record, 'field path'): Receive a constant defined above
 * 检查字段是否为键入的值为null的字段
 *                            to check if the field is typed field with value null
 * sdc。createRecord（String recordId）：创建新记录。
 *  sdc.createRecord(String recordId): Creates a new record.
 * 传递recordId以唯一标识记录，并包含足够的信息以跟踪记录源。
 *                            Pass a recordId to uniquely identify the record and include enough information to track down the record source.
 * sdc。createMap（布尔列表映射）：创建一个映射，用作记录中的字段。
 *  sdc.createMap(boolean listMap): Create a map for use as a field in a record.
 * 将true传递给此函数以创建列表映射（有序映射）
 *                            Pass true to this function to create a list map (ordered map)
 *
 * sdc。createEvent（字符串类型，int版本）：创建一个新事件。
 *  sdc.createEvent(String type, int version): Creates a new event.
 * 使用标准标题创建新的空事件。
 *                            Create new empty event with standard headers.
 * sdc。toEvent（记录）：将事件发送到事件流
 *  sdc.toEvent(Record): Send event to event stream
 * 仅限使用SDC函数创建的事件。支持createEvent。
 *                            Only events created with sdcFunctions.createEvent are supported.
 * sdc。isPreview（）：确定管道是否处于预览模式。
 *  sdc.isPreview(): Determine if pipeline is in preview mode.
 *
 * 可用的记录头变量：
 * Available Record Header Variables:
 *
 * 记录。属性：记录头属性的映射。
 *  record.attributes: a map of record header attributes.
 * 记录header name>：获取“header name”的值。
 *  record.<header name>: get the value of 'header name'.
 */

// Sample JavaScript code
var records = sdc.records;
for(var i = 0; i < records.length; i++) {
    try {
        
        //将记录根字段值更改为字符串值
        // Change record root field value to a STRING value
        // records[i].value = 'Hello ' + i;
        
        //将记录根字段值更改为映射值并创建一个条目
        // Change record root field value to a MAP value and create an entry
        // records[i].value = { V : 'Hello' };
        
        //访问地图条目
        // Access a MAP entry
        // records[i].value.X = records[i].value['V'] + ' World';
        
        //修改地图条目
        // Modify a MAP entry
        // records[i].value.V = 5;
        
        //创建一个数组条目
        // Create an ARRAY entry
        // records[i].value.A = ['Element 1', 'Element 2'];
        
        //访问数组条目
        // Access a Array entry
        // records[i].value.B = records[i].value['A'][0];
        
        //修改现有数组项
        // Modify an existing ARRAY entry
        // records[i].value.A[0] = 100;
        
        //将整型赋值给一个字段，值为null；
        // Assign a integer type to a field and value null;
        // records[i].value.null_int = NULL_INTEGER
        
        //检查该字段是否为NULL_INTEGER。如果是，请指定一个值
        // Check if the field is NULL_INTEGER. If so, assign a value
        // if(sdc.getFieldNull(records[i], '/null_int') == NULL_INTEGER)
        //    records[i].value.null_int = 123
        
        //直接访问底层数据收集器记录。用于只读操作。
        // Direct access to the underlying Data Collector Record. Use for read-only operations.
        // fieldAttr = records[i].sdcRecord.get('/value').getAttribute('attr')
        
        //使用映射字段创建新记录
        // Create a new record with map field
        // var newRecord = sdc.createRecord(records[i].sourceId + ':newRecordId');
        // newRecord.value = {'field1' : 'val1', 'field2' : 'val2'};
        // sdc.output.write(newRecord);
        //创建一个新地图并将其添加到原始记录中
        // Create a new map and add it to the original record
        // var newMap = sdc.createMap(true);
        // newMap['key'] = 'value';
        // records[i].value['b'] = newMap;
        
        //如果源使用整个_文件作为数据格式，则适用
        // Applies if the source uses WHOLE_FILE as data format
        // var input_stream = record.value['fileRef'].getInputStream();
        // try {
        //     input_stream.read(); //Process the input stream //处理输入流
        // } finally {
        //     input_stream.close()
        // }
        
        //修改标题属性条目
        // Modify a header attribute entry
        // records[i].attributes['name'] = records[i].attributes['first_name'] + ' ' + records[i].attributes['last_name']
        
        //获取带有字段名的记录头，例如获取sourceId和errorCode
        // Get a record header with field names ex. get sourceId and errorCode
        // var sourceId = records[i].sourceId
        // var errorCode = ''
        // if (records[i].errorCode) {
        //     errorCode = records[i].errorCode
        // }

//移除字段开始
      records[i].value.remove('id');
//移除字段结束
      
//处理时间戳转日期格式开始
      //records[i].value.date 		= getYMDhms(records[i].value['created_at'], 'yes');
      records[i].attributes.date	= getYMDhms(records[i].value['created_at'], 'yes');
      
      records[i].value.start_at 	= getYMDhms(records[i].value['start_at'], 'no');
//处理时间戳转日期格式开始

//处理字符串拆分开始
        var arr = records[i].value['fileInfo']['file'].split('/');
      
       	records[i].value.date = arr[3];
      
      	var arr_name = arr[4].split('+');
      
       	records[i].value.name = arr_name[0]+'.csv';
//处理字符串拆分结束

        // Write record to processor output
        sdc.output.write(records[i]);
    } catch (e) {
        // Send record to error
        sdc.error.write(records[i], e);
    }
}

//处理时间戳转日期格式方法
function getYMDhms(time, only_ymd)
{
  	if (time === 0) { return ''; }
  	var timezone = 8; // 目标时区时间，东八区
   	var offset_GMT = new Date().getTimezoneOffset(); // 本地时间和格林威治的时间差，单位为分钟
    if (time === '') { 
        var nowDate = new Date().getTime(); // 本地时间距 1970 年 1 月 1 日午夜（GMT 时间）之间的毫秒数
        var date = new Date(nowDate + offset_GMT * 60 * 1000 + timezone * 60 * 60 * 1000);
    }else{
      	var date = new Date(parseInt(time) * 1000 + offset_GMT * 60 * 1000 + timezone * 60 * 60 * 1000);
    }
	Y = date.getFullYear() + '-';
	M = (date.getMonth()+1 < 10 ? '0' + (date.getMonth()+1) : date.getMonth()+1) + '-';
	D = date.getDate() < 10 ? '0' + date.getDate() : date.getDate();
  	if(only_ymd == 'yes')
    {
      	return Y + M + D;
    }else{
      	h = ' ' + (date.getHours()) + ':';
		m = date.getMinutes() + ':';
		s = date.getSeconds();
		return Y + M + D + h + m + s;
    }
}


var date = new Date()；

Y = date.getUTCFullYear() + '-';

M = (date.getUTCMonth()+1 < 10 ? '0' + (date.getUTCMonth()+1) : date.getUTCMonth()+1) + '-';

D = date.getUTCDate() < 10 ? '0' + date.getUTCDate() : date.getUTCDate();

h = ' ' + (date.getUTCHours()) + ':';
  
m = date.getUTCMinutes() + ':';
  
s = date.getUTCSeconds();


/tmp/out/${YYYY()}-${MM()}-${DD()}
/tmp/out/${record:value('/date')}
/tmp/out/${record.attributes('/date')}❌
/tmp/out/${record:attribute('date')}✅