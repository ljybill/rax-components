[![npm](https://img.shields.io/npm/v/rax-scrollview.svg)](https://www.npmjs.com/package/rax-scrollview)
**描述：**
ScrollView 是一个包装了滚动操作的组件。一般情况下需要一个确定的高度来保证 ScrollView 的正常展现。
## 安装

```bash
$ npm install rax-scrollview --save
```
## 属性

注：
1、**支持**列表中的 <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" />代表h5 <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" />代表weex  <img alt="miniApp" src="https://gw.alicdn.com/tfs/TB1bBpmbRCw3KVjSZFuXXcAOpXa-200-200.svg" width="25px" height="25px" />代表小程序

|**属性**| **类型** | **默认值** | **必填** | **描述**           | **支持** |
| ----------- | ---------- | ---------- | ------------ | ------------------ | ------------ |
| scrollEventThrottle     | `number` | 100      |     false         | 这个属性控制在滚动过程中，scroll事件被调用的频率，用于滚动的节流 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" />|
| horizontal     | `boolean` | -          |      false        | 设置为横向滚动 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" /><img alt="miniApp" src="https://gw.alicdn.com/tfs/TB1bBpmbRCw3KVjSZFuXXcAOpXa-200-200.svg" width="25px" height="25px" />|
| showsHorizontalScrollIndicator     | `boolean` | true          |     false         | 是否允许出现水平滚动条 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" />|
| showsVerticalScrollIndicator     | `boolean` | true          |     false        | 是否允许出现垂直滚动条 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" />|
| onEndReachedThreshold     | `number` | 500         |     false         | 设置加载更多的偏移 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" /><img alt="miniApp" src="https://gw.alicdn.com/tfs/TB1bBpmbRCw3KVjSZFuXXcAOpXa-200-200.svg" width="25px" height="25px" />|
| onEndReached     | `function` | -          |     false         | 滚动区域还剩`onEndReachedThreshold`的长度时触发 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" /><img alt="miniApp" src="https://gw.alicdn.com/tfs/TB1bBpmbRCw3KVjSZFuXXcAOpXa-200-200.svg" width="25px" height="25px" />|
| onScroll     | `function` | -          |     false         | 滚动时触发的事件，返回当前滚动的水平垂直距离 | <img alt="browser" src="https://gw.alicdn.com/tfs/TB1uYFobGSs3KVjSZPiXXcsiVXa-200-200.svg" width="25px" height="25px" /> <img alt="weex" src="https://gw.alicdn.com/tfs/TB1jM0ebMaH3KVjSZFjXXcFWpXa-200-200.svg" width="25px" height="25px" /><img alt="miniApp" src="https://gw.alicdn.com/tfs/TB1bBpmbRCw3KVjSZFuXXcAOpXa-200-200.svg" width="25px" height="25px" />|
## 方法
### scrollTo({x:number,y:number})
#### 参数
参数为object，包含以下属性
| **属性** | **类型** | **默认值** | **必填** | **描述**            | 
| -------- | -------- | ---------- | ------------ | ------------------- |
| x  | `number` | -          | 否           | 横向的偏移量            | 
| y | `number` | -       | 否           | 纵向的偏移量 | 
## 示例
```jsx
import {createElement, Component, render,createRef} from 'rax';
import View from 'rax-view';

import DU from "driver-universal"
import Text from 'rax-text';
import ScrollView from 'rax-scrollview';

class Thumb extends Component {
  shouldComponentUpdate(nextProps, nextState) {
    return false;
  }

  render() {
    return (
      <View style={styles.button}>
        <View style={styles.box} />
      </View>
    );
  }
}

let THUMBS = [];
for (let i = 0; i < 20; i++) THUMBS.push(i);
let createThumbRow = (val, i) => <Thumb key={i} />;

class App extends Component {
  state = {
    horizontalScrollViewEventLog: false,
    scrollViewEventLog: false,
  };
  constructor(props) {
    super(props);
    this.horizontalScrollView = createRef();
  }

  render() {
    return (
      <View style={styles.root}>
      <View style={styles.container}>
        <ScrollView
          ref={this.horizontalScrollView}
          style={{
            height: 100,
          }}
          horizontal={true}
          onEndReached={() => this.setState({horizontalScrollViewEventLog:true})}
        >
          {THUMBS.map(createThumbRow)}
        </ScrollView>

        <View
          style={styles.button}
          onClick={() => {this.horizontalScrollView.current.scrollTo({x: 0})}}>
          <Text>Scroll to start</Text>
        </View>

        <View style={styles.eventLogBox}>
          <Text>{this.state.horizontalScrollViewEventLog ? 'onEndReached' : ''}</Text>
        </View>

      </View>

      <View style={{...styles.container, ...{height: 500}}}>
        <ScrollView
          ref={(scrollView) => {
            this.scrollView = scrollView;
          }}
          onEndReached={() => this.setState({scrollViewEventLog:true})}
        >
          <View>
            <View style={styles.sticky}>
              <Text>Cannot sticky</Text>
            </View>
          </View>

          <View style={styles.sticky}>
            <Text>Sticky view must in ScrollView root</Text>
          </View>

          {THUMBS.map(createThumbRow)}

        </ScrollView>

        <View
          style={styles.button}
          onClick={() => {this.scrollView.scrollTo({y: 0})}}>
          <Text>Scroll to top</Text>
        </View>

        <View style={styles.eventLogBox}>
          <Text>{this.state.scrollViewEventLog ? 'onEndReached' : ''}</Text>
        </View>

      </View>

      </View>
    );
  }
}

let styles = {
  root: {
    width: 750,
    paddingTop: 20
  },
  sticky: {
    position: 'sticky',
    width: 750,
    backgroundColor: '#cccccc'
  },
  container: {
    padding: 20,
    borderStyle: 'solid',
    borderColor: '#dddddd',
    borderWidth: 1,
    marginLeft: 20,
    marginRight: 20,
    marginBottom: 10,
  },
  button: {
    margin: 7,
    padding: 5,
    alignItems: 'center',
    backgroundColor: '#eaeaea',
    borderRadius: 3,
  },
  box: {
    width: 64,
    height: 64,
  },
  eventLogBox: {
    padding: 10,
    margin: 10,
    height: 80,
    borderWidth: 1,
    borderColor: '#f0f0f0',
    backgroundColor: '#f9f9f9',
  },
};

render(<App />, document.body, { driver: DU });

```
