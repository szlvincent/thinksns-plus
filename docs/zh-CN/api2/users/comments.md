# 用户收到的评论

```
GET /user/comments
```

#### 参数

| 名称 | 类型 | 描述 |
|:----:|:----:|----|
| limit | 整数 |获取的条数，默认 `20`。 |
| after | 整数 | 传递上次获取的最后一条 `id`。 |

##### 响应

```
Status: 200 OK
```
```json
[
    {
        "id": 17,
        "user_id": 4,
        "target_user": 4,
        "reply_user": 0,
        "body": "欧娜嘛嘛",
        "commentable_id": 61,
        "commentable_type": "feeds",
        "created_at": "2017-08-25 02:11:52",
        "updated_at": "2017-08-25 02:11:52",
        "commentable": {
            "id": 61,
            "user_id": 4,
            "feed_content": "死咯都饿",
            "feed_from": 3,
            "like_count": 0,
            "feed_view_count": 0,
            "feed_comment_count": 1,
            "feed_latitude": null,
            "feed_longtitude": null,
            "feed_geohash": null,
            "audit_status": 1,
            "feed_mark": 41503627078906,
            "pinned": 0,
            "pinned_amount": 0,
            "created_at": "2017-08-25 02:11:19",
            "updated_at": "2017-08-25 02:11:52",
            "deleted_at": null,
            "images": [
                {
                    "id": 69,
                    "file_id": 58,
                    "user_id": 4,
                    "channel": "feed:image",
                    "raw": "61",
                    "size": "750x1334",
                    "created_at": "2017-08-25 02:11:19",
                    "updated_at": "2017-08-25 02:11:19",
                    "deleted_at": null
                }
            ],
            "paid_node": null
        }
    },
]
```

| 字段 | 描述 |
|:----:|-----|
| id | 评论 ID。|
| user_id | 发布评论的人。|
| target_user | 接收评论的目标用户。|
| reply_user | 评论回复的人。|
| body | 评论内容 |
| commentable_id | 评论来源资源 ID，根据 `commentable_type` 判断是来自何处。|
| commentable_type | 评论所属资源类型。|
| images | 动态资源|
| id | file_with id|
| file_id | 图片ID|
| user_id | 发布用户ID|
| channel | 动态类型|
| raw | 动态ID|
| created_at | 评论创建时间。|
| updated_at | 评论更新时间。|
| commentable | 评论来源资料，如果来源被删除，则为 `null`。|
