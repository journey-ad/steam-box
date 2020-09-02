你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# 


<p align="center">
  <img width="400" src="https://user-images.githubusercontent.com/8252317/83985151-9e8eaf00-a96a-11ea-9b3c-b654dc9bee2f.png">
  <h3 align="center">steam-box</h3>
  <p align="center"><img width="20" height="20" src="https://store.steampowered.com/favicon.ico"></img>  Update  pinned gist / profile README to contain your Steam playtime leaderboard. </p>
  
   <p align="center">
    <a href="https://github.com/YouEclipse/steam-box/workflows/Update%20gist%20with%20Steam%20Playtime/badge.svg"><img src="https://github.com/YouEclipse/steam-box/workflows/Update%20gist%20with%20Steam%20Playtime/badge.svg" alt="Update gist with Steam Playtime"></a>
  </p>
</p>


---
English | [简体中文](./README_zh.md)

> 📌✨ For more pinned-gist projects like this one, check out: https://github.com/matchai/awesome-pinned-gists


## 💻 Setup

### 🎒 Prep work
> if only want's to update a markdown,like profile README,skip step 1 and step 2.
1. Create a new public GitHub Gist (https://gist.github.com/)
1. Create a token with the `gist` scope and copy it. (https://github.com/settings/tokens/new)
1. Create a Steam  API key. (https://steamcommunity.com/dev/apikey)
1. Find the steam ID of your account. (https://steamid.io)
1. For updating a markdown file，add comments to the place where you want to update in the markdown file.
   ```markdown
    <!-- steam-box start -->
    <!-- steam-box end -->
    
   ```


### 🚀 Project setup
1. Fork this repo
1. Edit the [environment variable](https://github.com/YouEclipse/steam-box/actions/runs/126970182/workflow#L17-L19) in `.github/workflows/schedule.yml`:

> For updating github profile README,you can follow [steam-box.yml](https://github.com/YouEclipse/YouEclipse/blob/master/.github/workflows/steam-box.yml) in [YouEclipse](https://github.com/YouEclipse/YouEclipse) to create a Action in your README repo.Remember it's unsafe to use token with **`repo`** scope for updating the repo, steam-box update the profile repo using git command in Github Action instead of using github API.

   - **GIST_ID:** The ID portion from your gist url: `https://gist.github.com/YouEclipse/`**`9bc7025496e478f439b9cd43eba989a4`**.

1. Go to the repo **Settings > Secrets**
1. Add the following environment variables:
   - **GH_TOKEN:** The GitHub token generated above.
   - **STEAM_API_KEY:** The steam API key you created above. 
   - **STEAM_ID:** The steam ID of your account. 
1. If you want to show specific games,put the ids in environmet variable **APP_ID**:
   - like `APP_ID=431960,730`
   - you can get the id of a game from the store url: `https://store.steampowered.com/app/`**730**`/CounterStrike_Global_Offensive/`

## 🕵️ How it works
- Get your games playtime from [Steamwork Web API](https://partner.steamgames.com/doc/webapi) 
- Update Gist with Github API 
- Use Github Actions for updating Gist  

## 📄 License
This project is licensed under [Apache-2.0](./LICENSE)
