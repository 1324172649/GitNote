首先关联一个类似的能关联得上的应用：
然后抓取到编辑接口，和请求参数，如下：
http://192.168.2.31/api/widget/d3776f3552ffc482cf2033ec85e54807

```language
{
    "id": "d3776f3552ffc482cf2033ec85e54807",
    "name": "未命名的组件1",
    "category": "image_text_card",
    "type": "image_text_card",
    "sub_type": "rich_graphic_round",
    "data_model": "",
    "data": [],
    "status": "1",
    "sys_id": "",
    "updated_at": 1654846337,
    "schema": {
        "authority": {
            "share_type": 1,
            "share_scope": []
        },
        "style": {
            "user_show_flag": 1,
            "source_type": "obj",
            "image": "/openfile/getfile?type=jw_n_image&id=o5iHOerofoOcAXQf",
            "title": "test",
            "desc": "",
            "extra_info": "",
            "users": [],
            "user_num": 10,
            "red_corner_mark": {
                "status": 2,
                "expire_at": 1655135999
            },
            "is_by_user_added": 2,
            "covers": {
                "big_graphic": "/dist/images/icons/df_cover/unknown_hor_b.png",
                "rich_graphic_top": "/dist/images/icons/df_cover/unknown_hor_s.png",
                "big_graphic_square": "/dist/images/icons/df_cover/unknown_ver_b.png",
                "rich_graphic_square": "/dist/images/icons/df_cover/unknown_ver_s.png",
                "rich_graphic_right": "/dist/images/icons/df_cover/unknown_ver_r.png",
                "big_graphic_third": "/dist/images/icons/df_cover/unknown_ver_r.png",
                "rich_graphic_round": "/dist/images/icons/df_cover/unknown_ver_r.png",
                "rich_graphic_right_oblong": "/dist/images/icons/df_cover/unknown_hor_b.png"
            }
        },
        "actions": [
            {
                "type": "act_jw_goto",
                "trigger": "ontap",
                "binding": {
                    "id": "show_app",
                    "appId": "a489df30d98f7f88e56b897e44c3b6f8",
                    "parentId": "a489df30d98f7f88e56b897e44c3b6f8",
                    "module": "index",
                    "sub_type": "7",
                    "obj_type": "jw_n_app",
                    "app_id": "a489df30d98f7f88e56b897e44c3b6f8",
                    "appType": "jw_app_nativern",
                    "obj": {
                        "id": 64,
                        "app_id": "17f927878b7208d2982e385ac05f9e4c",
                        "name": "test",
                        "en_name": "",
                        "th_name": "",
                        "parent_id": "17f927878b7208d2982e385ac05f9e4c",
                        "use_parent_share": "0",
                        "pinyin": "test",
                        "initial": "",
                        "logo": "/file/vieworiginal?id=o5iHOerofoOcAXQf",
                        "status": 2,
                        "description": "",
                        "type": 7,
                        "sort": 2,
                        "edit_auth": 3,
                        "moportal": 1,
                        "moportal_link": "",
                        "pcportal": 2,
                        "pcportal_link": "",
                        "quickportal": 2,
                        "share_type": 1,
                        "share_scope": [],
                        "tags": [],
                        "created_at": 1654846220,
                        "updated_at": 1654846220,
                        "app_category": "",
                        "sub_type": "",
                        "theme_color": "",
                        "project_name": "test",
                        "appcode": "123456",
                        "communic_proxy": "",
                        "smallapp": 2,
                        "safe_verifiy": 2,
                        "start_params": [],
                        "base_api": [
                            "getTicket",
                            "callPhone",
                            "getPhotos"
                        ],
                        "user_attr": [],
                        "creator": {
                            "id": "ca7360d706299b9a9a6ab3aa00bee418",
                            "name": "LunaLiu(LunaLiu`s)",
                            "type": "jw_n_user",
                            "pinyin": "LunaLiu",
                            "employee_id": "",
                            "email": "lunaliu@starbucks.hk",
                            "other_account": "",
                            "status": 0,
                            "dept": [
                                {
                                    "dept_id": "pPCS5PSoj9WczIt1",
                                    "title": null,
                                    "dept_name": "Luna的店",
                                    "status": 0,
                                    "title_id": ""
                                },
                                {
                                    "dept_id": "Yf1s7Q5fo72SK6r3",
                                    "title": null,
                                    "dept_name": "星巴克专用测试服务器",
                                    "title_id": ""
                                }
                            ],
                            "avatar": {
                                "avatar_s": "/public/images/avatar/ss.jpg",
                                "avatar_l": "/public/images/avatar/ll.jpg"
                            },
                            "company_domain": "725V83rpxAGqLgbv"
                        },
                        "desc": "",
                        "style": {
                            "image": "/openfile/getfile?type=jw_n_image&id=o5iHOerofoOcAXQf",
                            "title": "test",
                            "desc": "",
                            "extra_info": "",
                            "covers": {
                                "big_graphic": "/dist/images/icons/df_cover/unknown_hor_b.png",
                                "rich_graphic_top": "/dist/images/icons/df_cover/unknown_hor_s.png",
                                "big_graphic_square": "/dist/images/icons/df_cover/unknown_ver_b.png",
                                "rich_graphic_square": "/dist/images/icons/df_cover/unknown_ver_s.png",
                                "rich_graphic_right": "/dist/images/icons/df_cover/unknown_ver_r.png",
                                "big_graphic_third": "/dist/images/icons/df_cover/unknown_ver_r.png",
                                "rich_graphic_round": "/dist/images/icons/df_cover/unknown_ver_r.png",
                                "rich_graphic_right_oblong": "/dist/images/icons/df_cover/unknown_hor_b.png"
                            }
                        },
                        "app_type": "jw_app_rn",
                        "jw_url": "jw://jw_app_rn/17f927878b7208d2982e385ac05f9e4c/17f927878b7208d2982e385ac05f9e4c",
                        "obj_type": "jw_n_app"
                    }
                }
            }
        ]
    },
    "bind_id": "VrNwlq0Yn7vL5xby",
    "authority_flag": 1,
    "page_id": "5333e4c7a054529ddcaee7a1580fb2cf",
    "oid": "5fcc70029390c399708a59d44d7558ba",
    "parent_id": "2cafe6dbeca1e552248d7b3d401520e3",
    "sub_widget_flag": 1,
    "pinyin": "weimingmingdezujian",
    "creator_id": "ca7360d706299b9a9a6ab3aa00bee418",
    "created_at": 1654846337,
    "operation_flag": 0,
    "sub_wids": []
}
```

修改schema=》actions=》binding=》appId、parentId、app_id为要绑定的app_id，appType为要绑定的app_type(例如：jw_app_nativern)
然后builder模版点击发布即可