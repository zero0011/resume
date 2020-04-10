<template>
  <div class="bgc">
    <div class="box-flex">
      <div class="left"></div>
      <div class="content">
        <div class="name">朱帅</div>
        <div class="message">
          <div class="message_time">男 / 1998 / 2021 届</div>
          <div class="profession">本科 / 东华理工大学 / 网络工程专业</div>
          <div class="position">期待职位 : Web前端实习生 , node 实习生</div>
        </div>
        <!-- 联系方式 -->
        <div class="Contact_information">联系方式</div>
        <div class="information">
          <span class="phone information_index">手机 : 18307975813</span>
          <span class="email information_index">邮箱 : 2732237782@qq.com</span>
          <span class="weixin information_index">微信 : 18307975813</span>
        </div>
        <!-- 社交主页 -->
        <div class="Social">社交主页</div>
        <div class="social_mess">
          <span class="social_mess_index">
            <a href="https://github.com/zero0011" target="_blank">GitHub</a>
          </span>
          <span class="social_mess_index">
            <a href="https://leetcode-cn.com/u/zero0011/" target="_blank">LeetCode</a>
          </span>
          <span class="social_mess_index">
            <a href="https://juejin.im/user/5d2c2647f265da1bae392b7d" target="_blank">掘金</a>
          </span>
        </div>
        <!-- 技能清单 -->
        <div class="skill">技能清单</div>
        <ul class="skill_message">
          <li
            v-for="content in contents"
            :key="content"
            class="skill_message_index"
          >{{content.name}} : {{content.skill}}</li>
        </ul>
        <!-- 项目经历 -->
        <div class="project">项目经历</div>
        <ul class="project_index">
          <li v-for="project in projects" :key="project" class="project_index_li">
            <div class="time">
              {{project.time}}
              <span class="project_name"><a :href="project.href" target="_blank">{{project.title}}</a></span>
            </div>
            <div class="project_index_skill">
              技术栈 :
              <span class="project_index_skill_details">{{project.skill_details}}</span>
            </div>
            <ul class="project_includes">
              <li v-for="include in project.includes" :key="include">
                {{include.main}}
              </li>
            </ul>
          </li>
        </ul>
      </div>
      <div class="right"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contents: [
        {
          name: "前端技能",
          skill: "HTML/CSS , javaScript"
        },
        {
          name: "前端框架",
          skill: "Vue"
        },
        {
          name: "后端技术栈",
          skill: "express"
        },
        {
          name: "数据库",
          skill: "mysql , Sequelize"
        },
        {
          name: "版本管理工具",
          skill: "Git"
        },
        {
          name: "设计工具",
          skill: "Easy mock"
        },
        {
          name: "测试工具",
          skill: "Postman"
        }
      ],
      projects: [
        {
          time : '2020.3 - 2020.3',
          href : 'https://github.com/zero0011/Puzzle',
          title : '拼图游戏',
          skill : 'vue',
          includes : [
            {
              main : '该项目是一个 用 vue 写拼图小游戏'
            },
            {
              main : '已经实现的功能有:1.普通拼图功能2.自动拼图功能3. 游戏聊天室功能'
            },
            {
              main : '聊天室采用WebSocket技术,属于服务端推送技术.'
            },
            {
              main: '具体是使用socket.io,它是将websocket和polling机制封装成了通用的接口'
            },
            {
              main : '难点:自动拼图功能(8数码问题)'
            },
            {
              main : '解决:1.先判断该排列方式是否有解2.若有解,则通过BFS查找复原路径'
            }
          ]
        },
        {
          time: "2020.3 - 2020.4",
          href : 'https://github.com/zero0011/imitate_juejin',
          title: "仿掘金",
          skill_details: "vue + vuex + express + Sequelize + mysql",
          includes : [
            {
              main : '该项目是基于 vue 的模仿掘金的首页的项目'
            },
            {
              main : '前端 : Vue + Vuex(状态管理) + 原生ajax + 实现登录注册 以及 写文章 功能'
            },
            {
              main : '后端 : express + sequelize(ORM) + mysql +  权限认证(cookie/session) 实现 登录注册 以及 发表文章 接口'
            },
            {
              main : '难点 : 前端上传 markdown文件  以及 图片 文件',
            },
            {
              main : `前端解决方式 : 1.前端对大文件进行切片 , file.slice。 2.并发上传切片。 3. 发送合并请求 `
            },
            {
              main : '后端解决方式 : 1.跨域处理 2.接收切片 3. 创建读写流, 并发合并切片 ' 
            }
          ]
        }
      ]
    };
  }
};
</script>

<style>
.bgc {
  background-color: #eee;
}
.box-flex {
  display: flex;
  width: 100%;
  height: 100%;
  min-width: 1000px;
}
.left {
  width: 290px;
  background-color: #eee;
}
.right {
  width: 290px;
  background-color: #eee;
}
.content {
  flex: 1;
  background-color: #fff;
}
.name {
  margin-top: 50px;
  margin-left: 150px;
  color: #0072ffa6;
  font-size: 40px;
  font-weight: 800;
}
.message {
  margin-left: 150px;
  color: #888888;
  margin-top: 20px;
  font-weight: 900;
}
.Contact_information,
.skill,
.Social,
.project {
  margin-top: 20px;
  margin-left: 150px;
  color: #0072ffa6;
  font-size: 23px;
  font-weight: 800;
}
.information,
.social_mess {
  margin-top: 10px;
  margin-left: 150px;
}
.information_index {
  margin-right: 50px;
  color: #888888;
  font-weight: 900;
}
.social_mess_index {
  margin-right: 200px;
  font-weight: 900;
}
.social_mess_index a {
  text-decoration: none;
  color: #04d9b1;
}
.skill_message {
  margin-top: 20px;
  margin-left: 150px;
  color: #888888;
  font-size: 15px;
  font-weight: 1000;
  list-style: none;
}
.skill_message_index {
  height: 22px;
}
.project_index {
  margin-top: 20px;
  margin-left: 150px;
  color: #888888;
  font-size: 15px;
  font-weight: 1000;
  list-style: none;
}
.project_index_li {
  margin-bottom: 40px;
}
.project_index_li:last-child {
  margin-bottom: 50px;
}
.project_name {
  margin-left: 550px;
  color: #04d9b1;
}
.project_name a {
  text-decoration: none;
  color: #04d9b1;
}
.project_includes{
  margin-left: 20px;
}
</style>