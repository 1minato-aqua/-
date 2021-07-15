
<template>


<!--<div class="note" :style="note" style="height: 25px; width: 25px;">-->
    <div id="Header">
      <div class="topMenu" style="height:4.7rem;list-style: none;margin-bottom: 0%;">
        <el-menu :default-active="activeIndex" style="background-color:#1527C2;font-family: Verdana, Geneva, Tahoma, sans-serif;" class="el-menu-demo" mode="horizontal" @select="handleSelect">
          <div class="logo" style="width:10%;margin:1% 0 -3% 2%">
            <img src="./wpaddlelogo.png" alt="">
          </div>

          <div class="slogen" style="
            border-radius:2px;float:left;margin:0 0 0 13%;width:20%;height:8%">

            <div class="hd nav-wrapper" style="float:left;margin:-3.5% 0 0 0 ">
              <!-- <a style="font-size:2.5rem;
                               color: blue;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;">
         PaddleSearch</a>  -->
              <span   style="color:white;
                   font-family:微软雅黑;
                    float:right;
                   font-size:2.5rem;
                   letter-spacing:8px;
                   margin:4% 0 0 0%">双桨追踪</span>
            </div>

          </div>
          <div class="topmenu" >
            <!-- <el-menu :default-active="activeIndex" style="background-color:#1527C2" class="el-menu-demo" mode="horizontal" @select="handleSelect" > -->
            <div  class="fontmenu" style="margin:5% 0 0 46%;">

              <li @click="goHeader3"><a><p style="color:white; font-family:微软雅黑; margin-top:1.5px;font-size:1.1rem;">主页</p></a></li>
              <li><a href="tables.html"><p style="color:white; font-family:微软雅黑; font-size:1.1rem;"> 查询记录 </p></a></li>
              <li @click="gosetting" ><a><p style="color:white; font-family:微软雅黑; font-size:1.1rem;">系统设置 </p></a></li>
              <li @click="gocontract" style="margin-right:0%"><a><p style="color:white; font-family:微软雅黑; font-size:1.1rem;">联系我们</p></a></li>

            </div>

            <li style="padding-right: 0;margin-left:7%;">  <el-button @click="drawert = true" style="margin:-23% 0 0 0%; border:0;float:right;background-color:#1527C2">
  <span style="margin-left:-80%"> <svg t="1624674019066" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2142" width="48" height="48"><path d="M251.690667 855.466667A429.056 429.056 0 0 0 512 942.933333c97.792 0 187.989333-32.597333 260.309333-87.466666a260.266667 260.266667 0 1 0-520.661333 0z m-70.485334-67.242667a337.621333 337.621333 0 0 1 196.394667-244.053333 209.066667 209.066667 0 1 1 268.8 0 337.621333 337.621333 0 0 1 196.394667 244.053333A429.226667 429.226667 0 0 0 942.933333 512c0-237.994667-192.938667-430.933333-430.933333-430.933333C274.005333 81.066667 81.066667 274.005333 81.066667 512c0 105.088 37.632 201.386667 100.138666 276.224zM512 1019.733333C231.594667 1019.733333 4.266667 792.405333 4.266667 512S231.594667 4.266667 512 4.266667 1019.733333 231.594667 1019.733333 512 792.405333 1019.733333 512 1019.733333z m0-503.466666a132.266667 132.266667 0 1 0 0-264.533334 132.266667 132.266667 0 0 0 0 264.533334z" fill="#ffffff" p-id="2143" data-spm-anchor-id="a313x.7781069.0.i0" class="selected"></path></svg>
    <!-- <svg style="padding-bottom:-10%" t="1623927759527" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4187" width="48" height="48"><path d="M512.23624999 281.9196875a151.093125 151.093125 0 1 0 0 302.1871875 151.093125 151.093125 0 0 0 0-302.1871875z m0 362.6671875c-162.826875 0-256.0003125 56.8528125-270.18749998 164.26687499a392.9596875 392.9596875 0 0 0 540.26718749 0C768.2375 701.4396875 675.063125 644.586875 512.23624999 644.586875z m0 332.42625a453.33375001 453.33375001 0 0 1-323.73374999-770.773125A450.613125 450.613125 0 0 1 502.7965625 70.3465625h9.43968751a453.33375001 453.33375001 0 0 1 323.62687499 770.773125 450.6665625 450.6665625 0 0 1-314.13375 135.8934375h-9.49312501z" p-id="4188" fill="#515151"></path>
            </svg>   --></span>
            </el-button>

            </li>

          </div>

          <el-drawer
              title="我是标题"
              :visible.sync="drawert"
              :with-header="false"
              size="28%">
  <span >



  <div class="demo-type" style="margin:10% 0 0 44%">

    <div>
      <el-avatar :size="55" src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png"></el-avatar>
    </div>

  </div>

          <el-form :model="form" style="margin:10% 0 0 0%">

            <el-divider class="fgx"></el-divider>
     <div >

       <div style="background-color:#ECF5FF; ">
      <el-form-item  label="用户名：" :label-width="formLabelWidth" style="margin:0% 0 0 0">
            <label >admin</label>
      </el-form-item>

 <el-divider class="fgx" ></el-divider>
</div>



      <el-form-item label="密码：" :label-width="formLabelWidth" style="margin:0% 0 0 0">
           <label>******</label>
      </el-form-item>

 <el-divider class="fgx"></el-divider>

 <div style="background-color:#ECF5FF;">
      <el-form-item label="所属单位：" :label-width="formLabelWidth" style="background-color:#ECF5FF;margin:0% 0 0 0">
           <label>长春工业大学</label>

      </el-form-item>

 <el-divider class="fgx"></el-divider>
</div>
       <el-form-item label="注册时间：" :label-width="formLabelWidth" style="margin:0% 0 0 0">
           <label>2021.06.01</label>

      </el-form-item>

       <el-divider class="fgx"></el-divider>


 <div style="background-color:#ECF5FF;">
      <el-form-item label="权限范围：" :label-width="formLabelWidth" style="background-color:#ECF5FF;margin:0% 0 0 0">
           <label>校园监控</label>

      </el-form-item>

 <el-divider class="fgx"></el-divider>
</div>

      </div>
 <el-form-item label="上传记录："   style="margin:5% 0 0 1%">
      </el-form-item>
 <div class="block">
    <el-carousel  direction="vertical"  height="230px">
      <el-carousel-item v-for="item in 2" :key="item">

 <video-player  class="video-player vjs-custom-skin"
                id = "myVideo"
                ref="videoPlayer"
                :playsinline="true"
                :options="playerOptions"

 ></video-player>



        <h3 class="small">{{ item }}</h3>
      </el-carousel-item>
    </el-carousel>
  </div>

<el-form-item label="检测结果记录："   style="margin:5% 0 0 1%">
      </el-form-item>
            <!-- <span class="demonstration">检测结果记录</span> -->
   <div class="block">
    <el-carousel   direction="vertical"   height="230px">
      <el-carousel-item v-for="item in 2" :key="item">

 <video-player  class="video-player vjs-custom-skin"
                id = "myVideo"
                ref="videoPlayer"
                :playsinline="true"
                :options="playerOptions"

 ></video-player>



        <h3 class="small">{{ item }}</h3>
      </el-carousel-item>
    </el-carousel>
  </div>
    </el-form>
    <!-- <div style="margin:40% 0 0 30%;font-size:1.5rem;font-color:gray;font-family:宋体">

                 <label >用户名:11</label>

             <div >
                 <label>密码:111</label>
             </div>
              <div>
                 <label>更多设置</label>

             </div>

</div> -->

  </span>
          </el-drawer>


        </el-menu>

      </div>

  <div id="Content"  style="width: 100%;">

<!--            <el-dialog-->
<!--                    title="目标追踪中"-->
<!--                    :visible.sync="dialogTableVisibdddle"-->
<!--                    :show-close="false"-->
<!--                    :close-on-press-escape="false"-->
<!--                    :append-to-body="true"-->
<!--                    :close-on-click-modal="false"-->
<!--                    :center="true"-->
<!--            >-->
<!--                <el-progress :percentage="percentage"></el-progress>-->
<!--                &lt;!&ndash;    <span slot="footer" class="dialog-footer">请耐心等待约一分钟</span>  &ndash;&gt;-->
<!--            </el-dialog>-->

            <div id="aside" style="width:20%;margin-left:1%;margin-top:-7.5%">
                <el-card
                        class="rightMenu"
                        body-style="padding: 20px 5px 15px 10px"
                        style="width:100%; height:90%;background-color:#ffffff;
        margin-top: 30%;">

                <div id="test1" ></div>
                  
                 

    <div slot="header" class="clearfix" style="text-align: center" >

                    <div  style="margin-bottom:25px;"><p style="float:left;color:gray;font-weight:700;font-size:1rem;" >实时人数：</p>
                      <span  style="margin-top:50px;height:100px;width:100px;font-size:4em;color:#1527C2;">
                      <p >{{person}}</p></span></div> //id="app1" v-for="i in Values1" v-bind:key="i"

      <div style="padding-top:25px;border-top: 1px solid lightgray"><p style="float:left;color:gray;font-weight:700;font-size:1rem">检测人数：</p>
        <span  style="margin-top:1%;height:100px;width:100px;font-size:4em;color:#1527C2;">
          <p>{{person0}}</p></span></div>

                        <!-- <span class="steps" style="letter-spacing: 5px;font-size: 17px">行人追踪信息</span> -->
                    </div>

                  <el-switch
                      v-model="value1"
                      style="margin:8% 0 20% 5%;"
                      class="switchStyle"
                      active-text="检测模式"
                      inactive-text="视频模式"
                       active-color="#1527C2"
                      @change="handleSwitch($event, 1)"
                      >
                  </el-switch>
<!--                  <el-switch-->
<!--                      v-model="value2"-->
<!--                      style="margin:5% 0 20% 5%; font-size:2px; "-->

<!--                      @change="handleSwitch($event, 2)"-->
<!--                  >-->
<!--                  </el-switch>-->
                  <div class="zxd" style="width:100%;color:#1527C2;">
                    <p style="color:gray; margin-top:40px;font-weight:700;font-size:1rem;">阈值：</p>
                    <div class="block">
                      <el-slider
                          v-model="valuee"
                          :step="0.01"
                          :max="1"
                          :format-tooltip="changeA"
                          show-input>

                      </el-slider>

                    </div>

                  </div>
<!--                  formatTooltip-->
<!--                  onchange="changeA()"-->
<!--                  oninput="change()"-->

                  <el-button
                            v-show="showbutton"
                            icon="el-icon-upload2"
                            class="download_bt"           
                            v-on:click="true_upload"
                            style="margin:20% 0 0 20%;font-size:1rem;color:gray;font-weight:700;background-color: #ffffff;display: none;text-align:center"
                  >
                        上传文件
                        <input
                                ref="upload"
                                name="file"
                                type="file"
                                @change="upload"
                                style="margin-left: 30px;color: gray;background-color: #ffffff;display: none;"
                        />
<!--                    <input class="file" name="file" type="file" accept="video/mp4,video/webm,video/avi" @change="upload"/>-->

                    </el-button>

<!--                      v-show="showbutton"-->
<!--                      icon="el-icon-upload"-->
<!--                      class="download_bt"-->
<!--                      v-on:click="true_upload"-->
<!--                      style="margin:20% 0 0 10%;color: gray;background-color: #ffffff;display: none;text-align:center"-->

                  <el-button icon="el-icon-video-play" class="download_bt" style="margin:15% 0 0 20%;font-size:1rem;color:gray;font-weight:700;
                  background-color: #ffffff; text-align:center" @click="prepare">
                    开&#12288;&#12288;始

                    <!--                    <input class="file" name="file" type="file" accept="video/mp4,video/webm,video/avi" @change="upload"/>-->
                  </el-button>


                  <el-dialog
                      title="行人追踪检测中"
                      :visible.sync="dialogTableVisible"
                      :show-close="false"
                      :close-on-press-escape="false"
                      :append-to-body="true"
                      :close-on-click-modal="false"
                      :center="true"
                      style="margin-top:16vh;"
                  >
                    <el-progress :percentage="percentage"></el-progress>
                    <span slot="footer" class="dialog-footer"></span>
                  </el-dialog>
<!--                  <el-button icon="el-icon-upload" class="download_bt" style="margin:20% 0 0 10%;  color: gray;-->
<!--                  background-color: #ffffff; text-align:center" @click="send">-->
<!--                    播 放-->

<!--                    &lt;!&ndash;                    <input class="file" name="file" type="file" accept="video/mp4,video/webm,video/avi" @change="upload"/>&ndash;&gt;-->
<!--                  </el-button>-->
<!--                  <el-button icon="el-icon-upload" class="download_bt" style="margin:20% 0 0 10%;  color: gray;-->
<!--                  background-color: #ffffff; text-align:center" @click="open">-->
<!--                    open-->

<!--                    &lt;!&ndash;                    <input class="file" name="file" type="file" accept="video/mp4,video/webm,video/avi" @change="upload"/>&ndash;&gt;-->
<!--                  </el-button>-->
<!--                  <el-button icon="el-icon-upload" class="download_bt" style="margin:20% 0 0 10%;  color: gray;-->
<!--                  background-color: #ffffff; text-align:center" @click="mounted">-->
<!--                    aaa-->

<!--                    &lt;!&ndash;                    <input class="file" name="file" type="file" accept="video/mp4,video/webm,video/avi" @change="upload"/>&ndash;&gt;-->
<!--                  </el-button>-->
<!--                  <el-button icon="el-icon-upload" class="download_bt" style="margin:20% 0 0 10%;  color: gray;-->
<!--                  background-color: #ffffff; text-align:center" @click="beforeDestroy">-->
<!--                    bbb-->

<!--                    &lt;!&ndash;                    <input class="file" name="file" type="file" accept="video/mp4,video/webm,video/avi" @change="upload"/>&ndash;&gt;-->
<!--                  </el-button>-->
                </el-card>


                <!-- <div slot="error">
                    <div slot="placeholder" class="error">
                    </div>
                </div> -->

            </div>


            <!-- <div id="CT" style="width:90%; margin-top:5%; "> -->

                <!-- <div v-show="oneShow"  > -->

                    <!-- <el-card
                            id="maxVideo"
                            class="box-card"
                            style="width:90%"
  
                    > -->



  <el-tabs 
  style="width:73%;margin-top:-2.5%;margin-left:1%;margin-right:1%"
   v-model="activeName"
     active-color="#1527C2"
    type="border-card"
     @tab-click="handleClick">


    <el-tab-pane label="单镜头" name="second">
      <video-player  class="video-player vjs-custom-skin"
                     id = "myVideo0"
                     ref="videoPlayer"
                     :playsinline="true"
                     :options="playerOptions"
                     @play="PlayerPlay($event)"

      ></video-player></el-tab-pane>
    <el-tab-pane label="多镜头" name="first" >

<!--      <el-upload-->
<!--          class="upload-demo"-->
<!--          drag-->
<!--          :before-upload="beforeAvatarUpload"-->
<!--          action="https://jsonplaceholder.typicode.com/posts/"-->
<!--          multiple>-->
<!--        <i class="el-icon-upload"></i>-->
<!--        <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>-->
<!--      </el-upload>-->

      <video-player class="video-player1 video-js vjs-big-play-centered"

                    id = "myVideo"
                    ref="videoPlayer1"
                    :playsinline="true"
                    :options="playerOptions1"
                    @play="onPlayerPlay($event,index)"
                    src="./c_0.avi"


      ></video-player>
      <video-player  class="video-player1 video-js vjs-big-play-centered"
                     id = "myVideo"
                     ref="videoPlayer2"
                     style="margin-left: 6%"
                     :playsinline="true"
                     :options="playerOptions2"
                     @play="onPlayerPlay($event,index)"

      ></video-player>
      <video-player  class="video-player1 video-js vjs-big-play-centered "

                     id = "myVideo"
                     ref="videoPlayer3"
                     :playsinline="true"
                     :options="playerOptions3"
                     @play="onPlayerPlay($event,index)"
      ></video-player>
      <video-player  class="video-player1 video-js vjs-big-play-centered "
                     style="margin-left: 6%"
                     id = "myVideo"
                     ref="videoPlayer4"
                     :playsinline="true"
                     :options="playerOptions4"



      ></video-player>


      <el-row>

        <el-button type="primary" plain style="margin:0% 3% 0 25%;height:50px;width:150px;font-size:1.1rem;font-weight:700"  @click="gotostart">跨境追踪</el-button>
        <el-button type="primary" plain style="margin:0% 10% 0 10%;height:50px;width:150px;font-size:1.1rem;font-weight:700" @click="gotopause" >暂停全部</el-button>

      </el-row>
      <!--      <el-tab-pane label="单镜头" name="second">-->
<!--                   <video-player  class="video-player vjs-custom-skin"-->
<!--                                       id = "myVideo0"-->
<!--                                       ref="videoPlayer"-->
<!--                                       @play="onPlayerPlay($event)"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--&lt;!&ndash;                <video id="my_video">&ndash;&gt;-->
<!--&lt;!&ndash;                  <source src=""/>&ndash;&gt;-->
<!--&lt;!&ndash;                </video>&ndash;&gt;-->
<!--&lt;!&ndash;                    <video src="./../../../../date/12.mp4"></video>&ndash;&gt;-->

<!--&lt;!&ndash;                <div v-cloak>&ndash;&gt;-->

<!--&lt;!&ndash;                  <el-image :src="item" class="" style = 'height:100%;width:100%'/>&ndash;&gt;-->
<!--&lt;!&ndash;                </div>&ndash;&gt;-->



<!--              </el-tab-pane>-->
<!--               <el-tab-pane label="多镜头" name="first"  style="">-->
<!--                     <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo1"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                          <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo2"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                          <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo3"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                          <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo4"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                          <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo5"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                         <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo6"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                         <video-player  class="video-player1 vjs-custom-skin  "-->
<!--                -->
<!--                                       id = "myVideo7"-->
<!--                                       ref="videoPlayer"-->
<!--                                       :playsinline="true"-->
<!--                                       :options="playerOptions"-->

<!--                        ></video-player>-->
<!--                 -->
<!--                        -->
<!--                        -->
                        </el-tab-pane>




                
  </el-tabs>

  <el-card
                        class="leftMenu"
                        style="width: 23%; 
                        margin-right:1%;
                        height: 100%;background-color:#ffffff;
                         float: right;margin-top:-2.5%">


                    <div slot="header" class="clearfix" style="text-align: center; border-radius:none;" >
                        <span class="steps" style="color:gray;font-weight:600;letter-spacing:3px;font-size:1.5rem;font-family:微软雅黑; ">行人追踪信息</span>
                    </div>

    <div class="peoline" style="color: gray; height: 500px">

      <el-scrollbar style=" height:100%" >
      <table id="tid" class="table table-bordered table-hover" style="border-collapse: collapse;" >
        <thead style="width:100%">
        <tr>
          <th style="width:150px;font-size:0.9rem;font-weight:700;">行人图片</th>
          <th style="width:100px;padding-left:0px;font-size:0.9rem;font-weight:700;margin-left:170px" >行人ID</th>
        </tr>
        </thead>
        <tbody>
<!--        <tr> //v-for="(itme,index) in images" v-bind:key="index"-->
<!--          <td>-->
<!--            <img id="picture" :src=itme[0] alt="" width=40 height=80 />-->
<!--          </td>-->
<!--          <td>{{itme[1]}}</td>-->

<!--        </tr>-->
<!--        <tr>-->
<!--          <td>1</td>-->
<!--          <td><img src="./paddlelogo45.png" alt=""></td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>3</td>-->
<!--          <td><img src="./paddlelogo45.png" alt=""></td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>3</td>-->
<!--          <td><img src="./paddlelogo45.png" alt=""></td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>1</td>-->
<!--          <td><img src="./paddlelogo45.png" alt=""></td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>1</td>-->
<!--          <td><img src="./paddlelogo45.png" alt=""></td>-->
<!--        </tr>-->
        </tbody>
      </table>
        </el-scrollbar>
    </div>
<!--                    <div class="peoline" style="color: gray;">-->
<!--        -->

<!--              -->
<!--                        <div><a href="javascript:;" class=" getUpdate" style="font-size: 4px;color:gray; margin:10px 100px 100px 5px">时间：</a>  </div>-->
<!--                        <span class="steps" style="letter-spacing: 0px;font-size: 0.5em; margin-top:20px; margin-right:120px;margin-left: 5px">行人id：</span><br>-->
<!--&lt;!&ndash;                         <span class="steps" style="letter-spacing: 0px;font-size: 0.5em;margin-top:20px; margin-left: 5px">细节:</span><br>&ndash;&gt;-->
<!--&lt;!&ndash;                         <img style="float:contour" src="paddlelogo45.png" alt="">&ndash;&gt;-->
<!--                        <hr  style="color:lightgray" align=center width=300 color="gray" SIZE=1>-->

<!--&lt;!&ndash;                        <div><a href="javascript:;" class=" getUpdate" style="font-size: 4px;color:gray;margin:10px 100px 100px 5px">时间：</a></div>&ndash;&gt;-->
<!--&lt;!&ndash;                        <span class="steps" style="letter-spacing: 0px;font-size: 0.5em; margin-top:20px;margin-right:120px;margin-left: 5px">行人id：</span><br>&ndash;&gt;-->
<!--&lt;!&ndash;&lt;!&ndash;                       <span class="steps" style="letter-spacing: 0px;font-size: 0.5em;margin-top:20px;margin-left: 5px">细节:</span><br>&ndash;&gt;&ndash;&gt;-->
<!--&lt;!&ndash;&lt;!&ndash;                       <div style="float: right"><img src="paddlelogo45.png" alt=""></div>&ndash;&gt;&ndash;&gt;-->
<!--&lt;!&ndash;                        <hr align=center width=300 color=gray SIZE=1>&ndash;&gt;-->

<!--&lt;!&ndash;                        <div><a href="javascript:;" class=" getUpdate" style="font-size: 4px;color:gray;margin:10px 100px 100px 5px">时间：</a></div>&ndash;&gt;-->
<!--&lt;!&ndash;                        <span class="steps" style="letter-spacing: 0px;font-size: 0.5em; margin-top:20px;margin-right:120px;margin-left: 5px">行人id：</span><br>&ndash;&gt;-->
<!--&lt;!&ndash;&lt;!&ndash;                        <span class="steps" style="letter-spacing: 0px;font-size: 0.5em;margin-top:20px;margin-left: 5px">细节:</span><br>&ndash;&gt;&ndash;&gt;-->
<!--&lt;!&ndash;&lt;!&ndash;                       <div style="float: right"><img src="paddlelogo45.png" alt=""></div>&ndash;&gt;&ndash;&gt;-->
<!--&lt;!&ndash;                        <hr align=center width=300 color=gray SIZE=1>&ndash;&gt;-->
<!--                    </div>-->
                </el-card>


                      

                        <!-- <div class="demo-image__preview1">
                            <div
                                    v-loading="loading"
                                    element-loading-text="上传视频中"
                                    element-loading-spinner="el-icon-loading"
                            >
                        
                            </div>

                        
                                 
                        </div> -->


                        <!--          <el-card class="rightMenu" >-->
                        <!--            <div slot="header" class="clearfix" style="color: gray">-->
                        <!--              <span>行人信息</span>-->

                        <!--            </div>-->
                        <!--            <div class="text item" v-for="(value, name) in patient1" :key="name"  style="height: 150px;width: 150px;box-shadow: 0px 0px 5px #333333;border-radius:75px;background-color: rgb(41,49,225)">-->
                        <!--            <div v-for="(value, name) in patient" :key="name" class="text item">-->
                        <!--              <h3 class="span1" style="font-weight: normal;color: white;text-align: center;padding-top: 60px;">{{ name }}:{{ value }}</h3>-->


                        <!--            </div>-->
                        <!--            <div class="text item" v-for="(value, name) in patient2" :key="name">-->
                        <!--              <h3 style="font-weight: normal;color: white;">{{ name }}:{{ value }}</h3>-->
                        <!--            </div>-->




  

                <!--        </el-card>-->


                <!--     <progress percent="100" active='true' stroke-width="4" />

                       <template>
                         <div class='demo'>
                           <video-player class="video-player vjs-custom-skin"
                                         ref="videoPlayer"
                                         :playsinline="true"
                                         :options="playerOptions">
                           </video-player>
                         </div>
                       </template>
                -->




<!--        <div id="header-logo" style="padding:0 0 10px 20px ">-->

<!--            <img src="../../paddlelogo4.png" >-->

<!--        </div>-->

<!--        <div id="word" style="font-size: 23px;margin: 2px 0 0 300px">-->
<!--            <h1>{{ msg }}</h1>-->
<!--        </div>-->

    </div>
     </div>
<!--</div>-->
</template>


<script >



        // global range=document.getElementById('range');

        // function changeV() {    // eslint-disable-line no-unused-vars
        //
        //     console.log(range.value);
        //     var value = document.getElementById('range').value;
        //     document.getElementById('value').innerHTML = value;
        //
        // }
       
import axios from "axios";

    // document.addEventListener('DOMContentLoaded', function() {
    //     const getUpdate = document.querySelector('.getUpdate');
    //     const card = document.querySelector('.card');
    //     const close = document.querySelector('.close');
    //     getUpdate.addEventListener('click', e => {
    //         e.stopPropagation()
    //         card.style.display = 'flex';
    //     });
    //     close.addEventListener('click', e => {
    //         card.style.display = 'none';
    //     });
    //     document.addEventListener('click', e => {
    //         e.stopPropagation()
    //         if (e.target != card) {
    //             close.click()
    //         }
    //     })




        import global_variable from "./global_variable";
        // function keep() {
        //   console.log("keeping")
        // }
    // })
    //     var app1 = new Vue ({
    //       el: "#app1",
    //       data:{
    //         // src:"http://localhost:5000/./date/draw/image/2021-06-21/1234.mp4/1-3.jpg",
    //         Values:[
    //           // books= { id:'111' }
    //         ],
    //
    //         images:[],
    //         // url:""
    //       },
    //
    //       mounted:function(){
    //         this.fetchData();
    //       },
    //
    //       // template: '<div>${books}</div>',
    //       methods:{
            // fetchData(){
            //   axios
            //       .get("http://127.0.0.1:5000/search")
            //       .then(rsp=>{
            //         this.Values=rsp.data;
            //         console.log(this.Values);
            //
            //         //循环存入image 上面for j in len（） image【j】
            //         // console.log(this.books.length);
            //         // var max = 0;
            //         // for(var i=2; i < this.books.length; i++){
            //         //   var book = this.books[i];
            //         //   // console.log(book[5]);
            //         //   // console.log(typeof (book[5]));
            //         //   if(book[6] > max){
            //         //     max = book[6];
            //         //     var url = 'http://localhost:5000/' + book[5];
            //         //     // console.log(url);
            //         //     this.images.push([url,book[6], book[3], book[2]]);
            //         //   }
            //         // }
            //         // console.log(this.images);
            //         // this.src = "http://localhost:5000/./date/draw/image/2021-06-21/1234.mp4/1-3.jpg";
            //         //     console.log(url);
            //         //     document.getElementById('picture').src = url;
            //         //     // console.log(src);
            //         // }
            //         // document.getElementById('picture').src='http://localhost:5000/./date/draw/image/2021-06-21/1234.mp4/1-3.jpg'
            //       },err=>{console.log('Error')});
            // }
        //   },
        // })

    export default {


      range:document.getElementById('range'),

      data() {
            return {
              value4: 48,
              jiancewanbi:false,
              valuee: 0.5,
              time: false,
              state: false,

              j:1,
              form: {
                name: '',
                region: '',
                date1: '',
                date2: '',
                delivery: false,
                type: [],
                resource: '',
                desc: ''
              },
              formLabelWidth: '50%',

              drawert: false,

              note: {
                // backgroundImage: "url(" + require("./1.jpeg") + ")",
                backgroundRepeat: "no-repeat",
                backgroundSize: "25px auto",
                marginTop: "5px",
              },
              filename:"",
              gettime:"",
              durations:"",
              person:0,
              person0:0,
              player:"",
              cur_list:[],
              all_list:[],
              pic_list:[],
              id_list:[],
              images:[],
              images0:[],
              Values:[],
              Values1:[],

              z:0,
              timer: '',
              timer0: '',
              value: 0,
              datalist:[],

              item:'',
              ev:global_variable.ev,

              id:'',
              u:'',
              ESRTable: [],

              value1: true,
              value2: false,


                videoUploadPercent: "",
                //进度条的进度，
   // msg: "单/多镜头行人追踪系统",
                activeIndex: '1',
 // iframe路径
  reportUrl: "./contract.html",
                activeName: 'second',
                index : 0,
                index0: 0,
                oneShow: true,
                isShowUploadVideo: false,
                server_url: "http://127.0.0.1:5000",
                perimeter_picture_data: 0,
                area_picture_data: 0,
                // activeName: "first",
                active: 0,
                centerDialogVisible: true,
                url_1: "",
                url_2: "",
                textarea: "",
                srcList: [],
                srcList1: [],
                feature_list: [],
                feature_list_1: [],
                feat_list: [],
                url: "",
                visible: false,
                // activeName: "second",
                wait_return: "等待上传",
                wait_upload: "等待上传",
                loading: false,
                table: false,
                isNav: false,
                showbutton: true,
                percentage: 0,
                fullscreenLoading: true,
                opacitys: {
                    opacity: 0,
                },
                dialogTableVisible: false,

                patient1: {
                    // 人数

                },
                // patient2:{
                //   // 结果置信度："97%"
                // },
              playerOptions: {
                playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
                autoplay: false, //如果true,浏览器准备好时开始回放。
                muted: false, // 默认情况下将会消除任何音频。
                loop: false, // 导致视频一结束就重新开始。
                preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
                language: 'zh-CN',
                aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
                fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
                sources: [{
                  type: "video/mp4",//这里的种类支持很多种：基本视频格式、直播、流媒体等，具体可以参看git网址项目
                  // src:"12.mp4",
                  src: require("./MOT20-01-raw3.mp4")   //url地址
                  //url地址
                }],
                poster: require("./14.png"), //你的封面地址
                // width: document.documentElement.clientWidth, //播放器宽度
                notSupportedMessage: '此视频暂无法播放，请稍后再试', //允许覆盖Video.js无法播放媒体源时显示的默认信息。
                controlBar: {
                  timeDivider: true,
                  durationDisplay: true,
                  remainingTimeDisplay: false,
                  fullscreenToggle: true  //全屏按钮
                }
              },





              playerOptions1: {
                    playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
                    autoplay: false, //如果true,浏览器准备好时开始回放。
                    muted: false, // 默认情况下将会消除任何音频。
                    loop: false, // 导致视频一结束就重新开始。
                    preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
                    language: 'zh-CN',
                    aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
                    fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
                    sources: [{
                        type: "video/mp4",//这里的种类支持很多种：基本视频格式、直播、流媒体等，具体可以参看git网址项目
                      // src:"12.mp4",
                      src: require("./c_0.mp4")   //url地址
                      //url地址
                    }],
                    poster: require("./14.png"), //你的封面地址
                    // width: document.documentElement.clientWidth, //播放器宽度
                    notSupportedMessage: '此视频暂无法播放，请稍后再试', //允许覆盖Video.js无法播放媒体源时显示的默认信息。
                    controlBar: {
                        timeDivider: true,
                        durationDisplay: true,
                        remainingTimeDisplay: false,
                        fullscreenToggle: true  //全屏按钮
                    }
                },

              playerOptions2: {
                playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
                autoplay: false, //如果true,浏览器准备好时开始回放。
                muted: false, // 默认情况下将会消除任何音频。
                loop: false, // 导致视频一结束就重新开始。
                preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
                language: 'zh-CN',
                aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
                fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
                sources: [{
                  type: "video/mp4",//这里的种类支持很多种：基本视频格式、直播、流媒体等，具体可以参看git网址项目
                  // src:"12.mp4",
                  src: require("./c_1.mp4")   //url地址
                  //url地址
                }],
                poster: require("./14.png"), //你的封面地址
                // width: document.documentElement.clientWidth, //播放器宽度
                notSupportedMessage: '此视频暂无法播放，请稍后再试', //允许覆盖Video.js无法播放媒体源时显示的默认信息。
                controlBar: {
                  timeDivider: true,
                  durationDisplay: true,
                  remainingTimeDisplay: false,
                  fullscreenToggle: true  //全屏按钮
                }
              },


              playerOptions3: {
                playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
                autoplay: false, //如果true,浏览器准备好时开始回放。
                muted: false, // 默认情况下将会消除任何音频。
                loop: false, // 导致视频一结束就重新开始。
                preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
                language: 'zh-CN',
                aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
                fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
                sources: [{
                  type: "video/mp4",//这里的种类支持很多种：基本视频格式、直播、流媒体等，具体可以参看git网址项目
                  // src:"12.mp4",
                  src: require("./c_2.mp4")   //url地址
                  //url地址
                }],
                poster: require("./14.png"), //你的封面地址
                // width: document.documentElement.clientWidth, //播放器宽度
                notSupportedMessage: '此视频暂无法播放，请稍后再试', //允许覆盖Video.js无法播放媒体源时显示的默认信息。
                controlBar: {
                  timeDivider: true,
                  durationDisplay: true,
                  remainingTimeDisplay: false,
                  fullscreenToggle: true  //全屏按钮
                }
              },


              playerOptions4: {
                playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
                autoplay: false, //如果true,浏览器准备好时开始回放。
                muted: false, // 默认情况下将会消除任何音频。
                loop: false, // 导致视频一结束就重新开始。
                preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
                language: 'zh-CN',
                aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
                fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
                sources: [{
                  type: "video/mp4",//这里的种类支持很多种：基本视频格式、直播、流媒体等，具体可以参看git网址项目
                  // src:"12.mp4",
                  src: require("./c_3.mp4")   //url地址
                  //url地址
                }],
                poster: require("./14.png"), //你的封面地址
                // width: document.documentElement.clientWidth, //播放器宽度
                notSupportedMessage: '此视频暂无法播放，请稍后再试', //允许覆盖Video.js无法播放媒体源时显示的默认信息。
                controlBar: {
                  timeDivider: true,
                  durationDisplay: true,
                  remainingTimeDisplay: false,
                  fullscreenToggle: true  //全屏按钮
                }
              },



            };
        },
      // mounted:function(){
      //   this.fetchData()},
      sockets:{
        // events:{
        connect: function(){
          console.log('socket 连接成功');
        },
        message: function(val){
          console.log('返回:'+val);
          // this.jiancewanbi = true;
          // if(this.jiancewanbi == true){
          this.percentage = 100;
          this.dialogTableVisible = false;
          // }
          // var path = "./../../../.././date/raw/video/2021-06-21/12.mp4";
          var path = 'http://localhost:5000/' + val;
          // var path = val;
          // console.log(path)
          // this.playerOptions['sources'][0]['src'] =this.url;
          // this.item = path;

          // document.getElementById("myVideo0").src="./../../../.././date/raw/video/2021-06-21/12.mp4";
          this.playerOptions['sources'][0]['src']= path;
          // path.replace("video","image")
          // path = path + "/cover.jpg"
          // this.playerOptions['post'][0] = path;
          // document.getElementById("myVideo0").load();
          // console.log(this.playerOptions['sources'][0]['src'])

          // this.item = val;
          // this.datalist.push(val);
          //this.log_list.push(val);

        },

        begin : function(val){
          console.log(val);
        }
        // reconnecting () {
        //     console.log('尝试重新连接时触发')
        // },
        // }

      },

        methods: {


          formatTooltip(val) {
            return val;
          },

          handleAvatarSuccess(res, file) {
            this.imageUrl = URL.createObjectURL(file.raw);
          },

          beforeAvatarUpload(file) {
            const isJPG = file.type === 'video/mp4';
            const isLt2M = file.size / 10240000 / 10240000 < 2;

            if (!isJPG) {
              this.$message.error('上传视频只能是 MP4 格式!');
            }
            if (!isLt2M) {
              this.$message.error('上传视频大小不能超过10G!');
            }
            return isJPG && isLt2M;
          },

          gosetting(){
            this.$router.push("/setting")
          },

          goHeader3(){
            this.$router.push("/Header")
          },

          gocontract(){
            this.$router.push("/contract")
          },




          gotostart(){

            this.$refs.videoPlayer1.player.play();
            this.$refs.videoPlayer2.player.play();
            this.$refs.videoPlayer3.player.play();
            this.$refs.videoPlayer4.player.play();



          },

          gotopause(){
            this.$refs.videoPlayer1.player.pause()
            this.$refs.videoPlayer2.player.pause()
            this.$refs.videoPlayer3.player.pause()
            this.$refs.videoPlayer4.player.pause()

          },


          PlayerPlay(player) {
            console.log(player)
            // while (index<true){
            //
            //
            // }
            if (this.index0 > this.images0.length ){

              return ;
            }
            // if (!this.state) {
            //   // document.getElementById('myVideo0').loop = false // 不设置视频循环播放
            //   document.getElementById('myVideo0').addEventListener('ended', () => { //该视频播放是否已结束
            //     this.time = !this.time;
            //     this.state = true;
            //     console.log('ok');
            //   }, false)
            // }

            this.person=this.Values1[this.index];
            this.person0=this.images0[this.index0];
            var tableobj =document.getElementById("tid");
            var trobj =document.createElement("tr");
            var tdobj1=document.createElement("td");
            var image = document.createElement("img");
            image.setAttribute("src",this.images[this.index][0]);
            image.setAttribute("height",80)
            image.setAttribute("width",40)
            tdobj1.appendChild(image);
            trobj.appendChild(tdobj1);
            var tdobj2=document.createElement("td");
            tdobj2.innerHTML= this.images[this.index][1]
            trobj.appendChild(tdobj2);
            tableobj.appendChild(trobj);
            // console.log(this.Values1.length)
            console.log(this.Values1)
            console.log(this.images0)
            this.timer = setTimeout(()=>{   //设置延迟执行
              this.PlayerPlay();
              // console.log('ok');
            },1000);
            // if (this.index0 > this.Values1.length)
            //   return;
            // this.person0=this.images0[this.index0];
            // this.timer0 = setTimeout(()=>{   //设置延迟执行
            //   this.PlayerPlay();
            //   console.log('ok');
            //
            // },1000);

            this.index = this.index + 1 ;
            this.index0 = this.index0 + 1 ;

            // axios
            //     .get("http://127.0.0.1:5000/search")
            //     .then(rsp => {
            //       this.Values = rsp.data;
            //       console.log(this.Values);
            //       var value = 0;
            //       for(var j=2; j<this.Values.length; j++) {
            //         var jj = this.Values[j];
            //         if(value != jj[7]){
            //           value = jj[7];
            //           this.Values1.push(value);
            //         }
            //       }
            //       // var temp = 0;
            //       // for(var j=2; j<this.Values.length;j++) {
            //       //   var jj = this.Values[j];
            //       //   if(temp != jj[7]){
            //       //     value = jj[7];
            //       //     this.Values1.push(value);
            //       //   }
            //       // }
            //
            //
            //       var max = 0;
            //       for(var i=2; i < this.Values.length; i++) {
            //
            //         var book = this.Values[i];
            //         // if(this.filename == book[2]){
            //         if (book[6] > max) {
            //           max = book[6];
            //           var url = 'http://localhost:5000/' + book[5];
            //           console.log(url);
            //           this.images.push([url, book[6]]);
            //           // }
            //         }
            //       }
            //       // console.log(book[5]);
            //       // console.log(typeof (book[5]));
            //
            //
            //
            //
            //       var max0 = this.Values[1][7];
            //       for(var k=2; k < this.Values.length; k++) {
            //         var qwer = this.Values[k];
            //         // console.log(book[5]);
            //         // console.log(typeof (book[5]));
            //
            //
            //         if (qwer[6] > max0) {
            //           max0 = qwer[6];
            //
            //           this.images0.push(qwer[6]);
            //         }
            //         // console.log(this.images0);
            //       }
            //
            //     });
            // let mf = new Date().getMinutes()<10 ? '0'+new Date().getMinutes() : new Date().getMinutes();
            // let ss = new Date().getSeconds()<10 ? '0'+new Date().getSeconds() : new Date().getSeconds();
            // this.gettime = mf+':'+ss;
            // console.log(this.gettime)

            // this.durations = player.cache_.currentTime
              // console.log(' onPlayerTimeupdate!', this.durations)

          },
          // show(){
          //
          //
          // },

          // fetchData(){
          //   axios
          //       .get("http://127.0.0.1:5000/search")
          //       .then(rsp => {
          //         this.Values = rsp.data;
          //         // console.log(this.Values);
          //         var value = 0;
          //         for(var j=2; j<this.Values.length;j++) {
          //           var jj = this.Values[j];
          //           if(value != jj[7]){
          //             value = jj[7];
          //             this.Values1.push(value);
          //           }
          //         }
          //         // var temp = 0;
          //         // for(var j=2; j<this.Values.length;j++) {
          //         //   var jj = this.Values[j];
          //         //   if(temp != jj[7]){
          //         //     value = jj[7];
          //         //     this.Values1.push(value);
          //         //   }
          //         // }
          //
          //
          //         var max = 0;
          //         for(var i=2; i < this.Values.length; i++) {
          //
          //           var book = this.Values[i];
          //           // if(this.filename == book[2]){
          //             if (book[6] > max) {
          //               max = book[6];
          //               var url = 'http://localhost:5000/' + book[5];
          //               // console.log(url);
          //               this.images.push([url, book[6]]);
          //             // }
          //           }
          //         }
          //           // console.log(book[5]);
          //           // console.log(typeof (book[5]));
          //
          //
          //
          //
          //         var max0 = this.Values[2][7];
          //         for(var k=2; k < this.Values.length; k++) {
          //           var qwer = this.Values[k];
          //           // console.log(book[5]);
          //           // console.log(typeof (book[5]));
          //
          //
          //           if (qwer[6] > max0) {
          //             max0 = qwer[6];
          //
          //
          //             this.images0.push(qwer[6]);
          //           }
          //           // console.log(this.images0);
          //         }
          //
          //       });
          // },
          //
          //
          // // success: function (val) {
          // //   // if (data.rows.length > 0) {
          // //   document.getElementById("my_video").src = ;
          // //     // document.getElementById("my_video").play();
          // //   // } else
          // //   //   alert('暂无视频');
          // // },
          //
          // get() {
          //   this.value ++;
          //   console.log(this.value);
          //   this.item = this.datalist[this.value];
          // },
          // mounted() {
          //   this.timer = setInterval(this.get, 100);
          //   this.z++;
          // },
          // beforeDestroy() {
          //   clearInterval(this.timer);
          //   this.value = 0;
          // },
          // open(){
          //   //console.log("begin");
          //   for(var index in this.datalist) {
          //     setInterval(() => {
          //       //代码
          //
          //       // console.log(document.getElementById("fileImg").src);
          //       console.log(index)
          //       // setInterval(this.keep(index), 1000);
          //       console.log('keeping')
          //       this.item = this.datalist[index];
          //       // console.log(document.getElementById("fileImg").src);
          //
          //     }, 1000);
          //   }
          // },

        // aaa:function (){
        //   if(this.ev)
        //     this.update()
        //   else
        //     this.prepare();
        // },
          keep() {
          console.log("keeping");

        },
        prepare(){
          this.$socket.emit('message',encodeURI(this.ev));
          console.log(this.ev)
          this.dialogTableVisible = true;
          this.percentage = 0;
          setInterval(() => {
            this.myFunc();
          }, 1000);

          axios
              .get("http://127.0.0.1:5000/search")
              .then(rsp => {
                this.Values = rsp.data;
                console.log(this.Values);
                var value = 0;
                for(var j=2; j<this.Values.length; j++) {
                  var jj = this.Values[j];
                  if(value != jj[7]){
                    value = jj[7];
                    this.Values1.push(value);
                  }
                }
                // var temp = 0;
                // for(var j=2; j<this.Values.length;j++) {
                //   var jj = this.Values[j];
                //   if(temp != jj[7]){
                //     value = jj[7];
                //     this.Values1.push(value);
                //   }
                // }


                var max = 0;
                for(var i=2; i < this.Values.length; i++) {

                  var book = this.Values[i];
                  // if(this.filename == book[2]){
                  if (book[6] > max) {
                    max = book[6];
                    var url = 'http://localhost:5000/' + book[5];
                    console.log(url);
                    this.images.push([url, book[6]]);
                    // }
                  }
                }

                // console.log(book[5]);
                // console.log(typeof (book[5]));




                var max0 = this.Values[1][7];
                for(var k=1; k < this.Values.length; k++) {
                  var qwer = this.Values[k];
                  // console.log(book[5]);
                  // console.log(typeof (book[5]));

                  if (qwer[6] > max0) {
                    max0 = qwer[6];

                    this.images0.push(qwer[6]);
                  }
                  // console.log(this.images0);
                }

              });

          // axios
          //     .get("http://127.0.0.1:5000/search")
          //     .then(rsp => {
          //       this.Values = rsp.data;
          //       // console.log(this.Values);
          //       var value = 0;
          //       for(var j=2; j<this.Values.length;j++) {
          //         var jj = this.Values[j];
          //         if(value != jj[7]){
          //           value = jj[7];
          //           this.Values1.push(value);
          //         }
          //       }
          //       // var temp = 0;
          //       // for(var j=2; j<this.Values.length;j++) {
          //       //   var jj = this.Values[j];
          //       //   if(temp != jj[7]){
          //       //     value = jj[7];
          //       //     this.Values1.push(value);
          //       //   }
          //       // }
          //
          //
          //       var max = 0;
          //       for(var i=2; i < this.Values.length; i++) {
          //
          //         var book = this.Values[i];
          //         // if(this.filename == book[2]){
          //         if (book[6] > max) {
          //           max = book[6];
          //           var url = 'http://localhost:5000/' + book[5];
          //           // console.log(url);
          //           this.images.push([url, book[6]]);
          //           // }
          //         }
          //       }
          //       // console.log(book[5]);
          //       // console.log(typeof (book[5]));
          //
          //
          //
          //
          //       var max0 = this.Values[2][7];
          //       for(var k=2; k < this.Values.length; k++) {
          //         var qwer = this.Values[k];
          //         // console.log(book[5]);
          //         // console.log(typeof (book[5]));
          //
          //
          //         if (qwer[6] > max0) {
          //           max0 = qwer[6];
          //
          //
          //           this.images0.push(qwer[6]);
          //         }
          //         // console.log(this.images0);
          //       }
          //
          //     });
          // window.timer = setInterval(this.heartbeat, 130000);
          //F:\programs\Yolov5-Flask-VUE-master\front-end\src\components\MOT20-01-raw.mp4
        },
        send(){
          this.$socket.emit('message',encodeURI(this.msg));
          // window.timer = setInterval(this.heartbeat, 130000);
          //F:\programs\Yolov5-Flask-VUE-master\front-end\src\components\MOT20-01-raw.mp4
        },
        handleSwitch:function($event){
          // console.log('11');
          // console.log($event);
          global_variable.ev = $event;
          // console.log(global_variable.ev);
          this.ev = global_variable.ev;
          console.log(this.ev);
        },

          changeA:function() {    // eslint-disable-line no-unused-vars

            // console.log(range.value);
            console.log(this.valuee)
            // var value = document.getElementById('range').valuee;
            // console.log(value)
            axios
                  .post(this.server_url + "/getThreshold", this.valuee)
                  .then();
          },


          handleClick(tab, event) {
            console.log(tab, event);
          },

            handleSelect(key, keyPath) {
                console.log(key, keyPath);
            },


            // gocontract() {
            //     this.$router.push("/contract");
            // },
            
            changeSwitch(data) {
            if (data == "true") {
                this.oneShow = true;
            } else {
                this.twoShow = true;
            }
        },
     
        true_upload() {
            this.$refs.upload.click();
        },
        next() {
            this.active++;
        },
        // 获得目标文件
        getObjectURL(file) {
            var url = null;
            if (window.createObjcectURL != undefined) {
                url = window.createOjcectURL(file);
            } else if (window.URL != undefined) {
                url = window.URL.createObjectURL(file);
            } else if (window.webkitURL != undefined) {
                url = window.webkitURL.createObjectURL(file);
            }
            return url;
        },


     // search: function() {
     //   axios
     //
     //       .get(this.server_url + "/search")
     //       .then(response => {
     //         this.ESRTable = response.data;},
     //         error => {
     //           console.log(error);
     //
     //       });
     //
     // },

          upload(e){
            // this.dialogTableVisible = true;
            //
            // this.percentage = 0;
            // var timer = setInterval(() => {
            //   this.myFunc();
            // }, 1000);

            let file = e.target.files[0];
            let filename = e.target.files[0].name;

            let param = new FormData(); //创建form对象
            // console.log(this.ev)
            param.append('file',file);//通过append向form对象添加数据
            console.log(param.get('file')); //FormData私有类对象，访问不到，可以通过get判断值是否传进去
            param.append('fname',filename);//通过append向form对象添加数据
            console.log(param.get('fname'))

            axios.post('http://127.0.0.1:5000/upload',param,{headers:{'Content-Type':'application/x-www-form-urlencoded' }}, ) //请求头要为表单
                .then(response=>{
                  // this.percentage = 100;
                  // clearInterval(timer);
                  //
                  // console.log(response.data);

                  this.filename = response.data;
                  console.log(this.filename);
                  this.playerOptions['poster']= response.data;
                  //
                  // this.dialogTableVisible = false;
                })
                .catch(function (error) {
                  console.log(error);
                })
          },


   // 上传文件
        update: function () {
              axios
                .post("http://127.0.0.1:5000/update")
                .then((response) => {
                  alert('111')
                    this.id = response.data.a;

                });
        },
        myFunc() {
            if (this.percentage + 33 < 99) {
                this.percentage = this.percentage + 33;
            } else {
                this.percentage = 99;
            }
        },
        drawChart() {
        },
        // notice1() {
        //     this.$notify({
        //         title: "预测成功",
        //         message: "点击图片可以查看大图",
        //         duration: 0,
        //         type: "success",
        //     });
        // },
      fullscreenToggle(){

      }

        }
    }



</script>
<!--<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js" type="text/javascript" charset="utf-8"></script>-->
<!--<script src="https://unpkg.com/axios/dist/axios.min.js" type="text/javascript" charset="utf-8"></script>-->
<!--<script src="https://unpkg.com/http-vue-loader"></script>-->
<!--<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>-->
<!--<script>-->

<!--import axios from "axios";-->

<!--Vue.options.delimiters = ['${', '}'];-->

<!--Vue.component('todo-item', {-->
<!--  props: ['todo'],-->
<!--  template: '<td>{{item}}</td>'-->
<!--});-->

<!--  var app1 = new Vue({-->
<!--    el:"#app1",-->
<!--    data:{-->
<!--      Values:[],-->
<!--    },-->
<!--    mounted:function() {-->
<!--      this.fetchData()-->
<!--    },-->

<!--  methods:{-->
<!--    fetchData(){-->
<!--      axios-->
<!--          .get("http://127.0.0.1:5000/search")-->
<!--          .then(rsp => {-->
<!--            this.Values = rsp.data;-->
<!--            console.log(this.Values);-->
<!--          },err => {-->
<!--            console.log('Error')-->
<!--          });-->
<!--    },-->
<!--  }-->
<!--  })-->
<!--</script>-->
<style> .upload-demo .el-upload-dragger {
  background-color: #fff;
  border-radius: 6px;
  box-sizing: border-box;
  width: 730px;
  height: 480px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.el-upload-dragger .el-icon-upload {
  font-size: 67px;
  color: #C0C4CC;
  margin: 160px 0 0 16px;
  line-height: 50px;
}

.fgx{
  margin:4% 0 4% 0;
}


.el-divider--horizontal {
  display: block;
  height: 1px;
  width: 100%;
  margin:0;
}



.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}



.el-tabs--border-card>.el-tabs__header .el-tabs__item.is-active {
  color: #1527C2;
  background-color: #FFF;
  border-right-color: #DCDFE6;
  border-left-color: #DCDFE6;
}

.el-tabs--border-card>.el-tabs__header .el-tabs__item:not(.is-disabled):hover {
  color: #1527c2;
}

.zxd{
  color:white;
}


.switchStyle .el-switch__label {
  /* font-size: 5rem; */
  color: gray;
}

.el-switch__label * {
  margin-top: -10%;
  margin-left: 10px;
  color:gray;
  line-height:2;
  font-weight: 600;
  font-size:1rem;
  display: inline-block;
}

.el-switch__label--left {
  margin:-5px  3px 0 0;
}

.el-switch__label--right {
  margin-left: -0px 0 0 0px;
}

.el-tabs__item {
  padding: 0 20px;
  height: 40px;
  box-sizing: border-box;
  line-height: 40px;
  display: inline-block;
  list-style: none;
  font-size: 1rem;
  font-weight: 500;
  position: relative;
}

.fontmenu{
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  padding-right: 18%;
  margin-left: 20%;
}

.slogen{
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

.video-player1{
  width: 42%;
  height:20%;
  float: left;

  margin:2% 4% 3% 0;
}


.topmenu{
  margin-top:-6%;

  background-color:#1527C2;
  font-family: 微软雅黑;
  width:72%;
  float:right;
}


.topMenu{
  background-color:#1527C2;

}

.topMenu li{
  padding-right: 0%;
  background-color: 1527C2;
  float:left;
  height: 2%;
  text-align: center;
  margin-left: 9%;
}

.topMenu li a{
  color: white;
  font-size:0.8rem;float:right;margin-top:3%;margin-left:0%;

}


.topMenu li a:hover{
  color: skyblue;
}

#Header {
  background-color:blue;
  /* margin-top: 2px; */
  /*float: left;*/
  height: 16%;
  margin-bottom: -5%;
  /*padding: 20px 50px 0 90px;*/
  /*width: 90%;*/
  /* margin: 10px auto;*/
}




.el-menu-demo {
  float: right;
  width: 100%;
  text-decoration: none;
}




.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both;
}


.rightMenu{
  /* margin-top: 60px; */
  color: white;

}

.demo-image__preview1 {

  width: 250px;
  height: 290px;
  /*margin: 20px 60px;*/
  float: left;
  background-color: #ffffff;
}

.error {
  margin: 100px auto;
  width: 50%;
  padding: 10px;
  text-align: center;
  background-color: #ffffff;
}

div {
  display: block;
}

.block-sidebar .block-sidebar-item:hover {
  color: gray;
}

#Content {

  /* height: 800px; */
  margin: 55px auto;
  display: flex;
  position: absolute;

}

#info_patient {
  margin-top: 10px;
  margin-right: 160px;
}

.el-slider__runway.show-input {
  margin:15% 3px 0 3px;
  width: auto;
}

.el-slider__input {
  float: right;
  margin-right: 10px;
  margin-top: -25px;
  width: 130px;
}


.el-tabs--border-card>.el-tabs__header .el-tabs__item.is-active {
  color: #1527C2;
  font-weight: 700;
  background-color: #FFF;
  border-right-color: #DCDFE6;
  border-left-color: #DCDFE6;
}

.el-tabs--bottom .el-tabs--left>.el-tabs__header .el-tabs__item:last-child, .el-tabs--bottom .el-tabs--right>.el-tabs__header .el-tabs__item:last-child, .el-tabs--bottom.el-tabs--border-card>.el-tabs__header .el-tabs__item:last-child, .el-tabs--bottom.el-tabs--card>.el-tabs__header .el-tabs__item:last-child, .el-tabs--top .el-tabs--left>.el-tabs__header .el-tabs__item:last-child, .el-tabs--top .el-tabs--right>.el-tabs__header .el-tabs__item:last-child, .el-tabs--top.el-tabs--border-card>.el-tabs__header .el-tabs__item:last-child, .el-tabs--top.el-tabs--card>.el-tabs__header .el-tabs__item:last-child {
  padding-right: 20px;
  font-weight: 700;
}

.el-switch__label--left {
  margin: 0px 3px 0 0;
}

/* .el-switch__label * {
    margin-top: -9%;
    color: #515151;
    line-height: 2;
    font-size: 1rem;
    display: inline-block;
} */

.el-switch__label--right {
  margin-left: 2px;
}


</style>


