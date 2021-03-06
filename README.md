# 效果
微信效果图：
![defalut style.gifo动](https://github.com/TalkingJourney/SCIndexView/blob/master/SCIndexViewDemo/Snapshots/demo_default.gif)
toast效果图：
![center toast style.gifo动](https://github.com/TalkingJourney/SCIndexView/blob/master/SCIndexViewDemo/Snapshots/demo_center_toast.gif)

# 功能及优点
主要功能及优点如下：
1. 当滑动UITableView列表时，索引视图的索引位置会跟着移动；
2. 当滑动UITableView列表时，另一根手指再滑动索引视图，列表滑动事件失效；
3. 当滑动索引视图时，会有指示器或者toast提示当前索引位置；
4. 当滑动索引视图时，不可以点击或者滑动UITableView列表；
5. 可以任意定制指示器、toast、索引视图的大小，文字颜色大小，间距等UI样式。

# 使用方法
可以通过CocoaPods导入，支持iOS7及以上。
pod 'SCIndexView'

### 1.x版本
1. 创建SCIndexViewConfiguration对象，这个对象用来控制索引的UI样式；
2. 创建SCIndexView对象，这个对象是索引视图本身，初始化方法必须传入UITableView列表，和SCIndexViewConfiguration对象；
3. 将SCIndexView索引视图添加到UITableView列表视图的父视图之中，再设置索引视图的数据源。

```
SCIndexViewConfiguration *indexViewConfiguration = [SCIndexViewConfiguration configuration];
SCIndexView *indexView = [[SCIndexView alloc] initWithTableView:self.tableView configuration:indexViewConfiguration];
indexView.translucentForTableViewInNavigationBar = self.translucent;
[self.view addSubview:indexView];
indexView.dataSource = indexViewDataSource;
```

### 2.x版本
1. 创建SCIndexViewConfiguration对象，这个对象用来控制索引的UI样式；
2. 设置UITableView对象的 sc_translucentForTableViewInNavigationBar 和 sc_indexViewConfiguration；
3. 再设置UITableView对象的索引数据源。
不用再关心SCIndexView视图本身，直接在UITableView上设置即可。

```
SCIndexViewConfiguration *indexViewConfiguration = [SCIndexViewConfiguration configuration];
tableView.sc_indexViewConfiguration = indexViewConfiguration;
tableView.sc_translucentForTableViewInNavigationBar = YES;
tableView.sc_indexViewDataSource = indexViewDataSource;
```

# 结束
如果大家有什么想法的话，可以向我反馈。如果大家喜欢的话，也可以通过star来鼓励下我，感谢大家捧场。
