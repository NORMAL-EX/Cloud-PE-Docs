# 日志
## 开发状态

### Cloud-PE 主体核心
* 基于 Windows11 23H2 母盘制作的内核
<Badge type="tip">版本：{{ iso_version }}</Badge> <Badge type="info">作者： Cloud-PE 开发团队</Badge> <Badge type="warning">版本类型：Stable</Badge>
:::info 母盘信息
22635.3066.240113-0519.NI_RELEASE_SVC_BETAFLT_PROD1_CLIENTMULTI_X64FRE_ZH-CN.ISO
:::

### Cloud-PE One

* 技术栈： Tauri、Rust、TypeScript、Vite、React、Coss UI
<Badge type="tip">版本：{{ hub_version }}</Badge> <Badge type="info">作者：dddffgg & Hello,World!</Badge> <Badge type="warning">版本类型：Stable</Badge>

:::tip 提示
🎉Cloud-PE One 近期已从 Semi Design 成功迁移到 Coss UI（迁移重构总计耗时：1天）
:::

<script>  
export default {  
  data() {  
    return {  
      iso_version: '获取中...',
      hub_version: '获取中...',
    };  
  },  
  methods: {  
    fetchInfo() {  
      fetch('https://api.cloud-pe.cn/GetInfo/')  
        .then(response => {  
          if (!response.ok) {  
            throw new Error('Network response was not ok');  
          }  
          return response.json();  
        })  
        .then(data => {  
          this.iso_version = data.data.cloud_pe === 'null' ? '获取失败' : `Cloud-PE ${data.data.cloud_pe}`;
          this.hub_version = data.hub_new.hub_ver === 'null' ? '获取失败' : `Cloud-PE One ${data.hub_new.hub_ver}`; 
        })  
        .catch(error => {  
          console.error('There was a problem with your fetch operation:', error);  
          this.iso_version = '获取失败';  
          this.hub_version = '获取失败';  
        });  
    }  
  },  
  mounted() {  
    this.fetchInfo();  
  }  
};  
</script>  