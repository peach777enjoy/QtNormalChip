```c++

// 构造QJSonObject
    QJsonObject json_object;
    json_object.insert(J_ID,        "1263");
    json_object.insert(J_NICK,      "lin");
    json_object.insert(J_AGE,       20);
    json_object.insert(J_ZHUANYE,   "ruanjiangc");

    // 转换成QByteArray
    QByteArray byte_array = QJsonDocument(json_object).toJson();

    // QByteArray转换成QJsonObject
    QJsonObject json_object2 = QJsonDocument::fromJson(byte_array).object();
    qDebug() << json_object2.value(J_ID).toString();
    qDebug() << json_object2.value(J_NICK).toString();
    qDebug() << json_object2.value(J_AGE).toInt();
    qDebug() << json_object2.value(J_ZHUANYE).toString();
```