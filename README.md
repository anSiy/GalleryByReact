遍历JSON，把图片的路径信息放进去

重新遍历新JSON，把它分解成16张 ，初始化位置，同时把各自信息（文字，位置）传递给各自图片

1.文字图片：data={value（来自JSON）} src={this.props.data.imageURL}

2.位置 componentDidMount （this.rearrange(0)(方法)） this.setState（执行） 确定各自的的位置 ：第一张放中间 第二张放where 最后一张放top

（arrange={this.state.imgsArrangeArr[index]}（真执行）） 完成后，同步给各自的图片，每张图片自己来领取自己的信息

各自的图片把自己的位置信息领回家，用一个袋装起来 styleObj = this.props.arrange.pos;

放在自己的style里 style={styleObj} } 打包所有图片，render出来{}

3.点击时，调用rearrange（this） (1)（this移动到中心，其他图片重排（方法）） ：调用rearrange()函数 (2)this.setState（执行） ：位置信息变为中心 (3)（arrange={this.state.imgsArrangeArr[index]}（真执行）） 把这个信息交给html 绑定，最后才显示

4.imageDatas.forEach 把JSON分解为16个 给定图片信息 和 位置 arrange={this.state.imgsArrangeArr[index]} 传给每个图片的位置，通过 this.props.arrange.pos 挂钩起来

5. (1) 初始化Constant (2) componentDidMount结束时： 计算出Constant内的各取值范围，执行rearrange函数 (3) getInitialState初始化:建立数组imgsArrangeArr: imageDatas.forEach this.state.imgsArrangeArr[index].pop 让每个图片都有imgsArrangeArrindex 执行rearrange函数 Constant.h.x imgsArrangeArr[i].pos = Constant.h.x (1.2+3)的结果:每个图片的位置确定
