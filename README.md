# top-postop-scrolltop-scrollHeight-offsetHeight
top-postop-scrolltop-scrollHeight-offsetHeight


1. top


            此属性仅仅在对象的定位(position)属性被设置时可用。否则，此属性设置会被忽略。

           <div style="background-color:red; position:absolute; width:100px; height:100px;">

             <p style="background-color:silver; position:absolute; top:-5px;">测试top</p>
          </div>

           上面是一个段落P包含在一个DIV内，可以看到P的top设置为-5px后，它的上边距超过了容器DIV的上边距，
           超过的这段距离就是设置的5px。需要注意的是，DIV和P这一对包含元素，
           都需要设置position为absolute才能得到想要的结果，假如父元素不设置，
           则子元素的参照将是更上层定义过position的元素，直到整个文档；


2. posTop


              posTop的数值其实和top是一样的，但区别在于，top固定了元素单位为px，
              而posTop只是一个数值(这一点可以通过alert("top="+id.style.top)和
              alert("posTop="+id.style.posTop)来证明)，因此一般使用posTop来进行运算。

              <div style="background-color:red; position:absolute; width:100px; height:100px;">

              <p id="test" style="background-color:silver; position:absolute;">测试posTop</p>

              </div>

              <script>
              test.style.posTop = 15+8;
              alert("top="+test.style.top);
              alert("posTop="+test.style.posTop);
              </script>
              无论你使用top或posTop来赋值，最后的结果都是一致的





3. scrollTop

          <div id="container" style="background-color:silver;
                  width:100px; height:100px; overflow:auto;">    
             <p style="background-color:red;">
              别再做情人 做只猫 做只狗 不做情人 做只宠物至少可爱迷人 和你相交不浅无谓明日会被你憎
             </p>
          </div>

          <script>
           var text=	document.getElementById("container")
             text.scrollTop = 32;
          </script>
          这一段文本在这个100*100的DIV内无法完全显示，所以设置了overflow为auto，
          它会出现一个上下方向的滑动框，假如没有设置id.scrollTop属性的话，
          默认情况下滑块位置在顶端。而设置了scrollTop值为12后，滑块的位置改变了，
          默认显示是卷过了12个象素的文本。如果设置overflow为hidden，则将会无法显示顶部12个象素的文本。

          注意设置方式是id.scrollTop，而不是id.style.scrollTop。



4. scrollHeight 与 offsetHeight


                offsetHeight是自身元素的高度，scrollHeight是 自身元素的高度+隐藏元素的高度。

                <div id="container" style="background-color:silver; width:100px; 
                    height:100px; overflow:auto;">
                  <p style="background-color:red; height:250px; ">
                别再做情人 做只猫 做只狗 不做情人 做只宠物至少可爱迷人 和你相交不浅无谓明日会被你憎
                  </p>
                </div>

                <script>
                alert(container.offsetHeight);
                alert(container.scrollHeight);
                </script>
                将依次输出100，250。因为已经指定了元素的height为100px，所以offsetHeight始终为100px；
                内部元素为250px，而容器元素只有100px，那么还有150px的内容它无法显示出来，
                但它却是实际存在的，所以scrollHeight值为100+150=250。




getBoundingClientRect()

http://www.cnblogs.com/qieqing/archive/2008/10/06/1304399.html


