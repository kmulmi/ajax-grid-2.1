
***Ajax-grid-2.1***
-------------------

**
This is a plugin give simple masonry gird layout 

    You can use this plugin by applying following code

***Sample Html Div***

    <div>
        <input type="text" onkeyup="filterPost(this)" />
        <div id="blog-sample">
            <h1>{id}</h1>
            <div><h3>{phone}</h3></div>
            <div>{address}</div>
        </div>
    </div>

***javascript code***

    <script>
        $('#blog-sample').ajaxGrid({
            "url": "repository/request_handler.php",
            "limit": 6,
            "columns": [
                {
                    mRender: function (row) {
                        var a = {};
                        a['phone'] = ' <a href="blog/blog-detail?id=' + row.phone + '">' + row.phone + '</a>';
                        a['address'] = row.address;
                        a['id'] = row.id;
                        return a;
                    }
                }/*,
                {"data": "id"},
                {"data": "address"},*/
            ],
            "previous": "&larr; Newer",
            "next": "Older &rarr;"
        });
    </script>
