<template>
  <div>
    <h2>{{ $t('app.aside.nav.form') }}</h2>
    <p class="tip">查看 <router-link class="link" :to="{name: 'VXEAPI', params: {name: 'form'}}">API</router-link></p>

    <p>
      <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent">
        <vxe-form-item title="名称" field="name">
          <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname">
          <vxe-input v-model="formData1.nickname" placeholder="请输入昵称"></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex">
          <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
            <vxe-option value="1" label="女"></vxe-option>
            <vxe-option value="2" label="男"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item>
          <vxe-button type="submit" status="primary">默认尺寸</vxe-button>
        </vxe-form-item>
      </vxe-form>
      <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent" size="medium">
        <vxe-form-item title="名称" field="name">
          <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname">
          <vxe-input v-model="formData1.nickname" placeholder="请输入昵称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex">
          <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
            <vxe-option value="1" label="女"></vxe-option>
            <vxe-option value="2" label="男"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item>
          <vxe-button type="submit" status="primary">中等尺寸</vxe-button>
        </vxe-form-item>
      </vxe-form>
      <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent" size="small">
        <vxe-form-item title="名称" field="name">
          <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname">
          <vxe-input v-model="formData1.nickname" placeholder="请输入昵称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex">
          <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
            <vxe-option value="1" label="女"></vxe-option>
            <vxe-option value="2" label="男"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item>
          <vxe-button type="submit" status="primary">小型尺寸</vxe-button>
        </vxe-form-item>
      </vxe-form>
      <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent" size="mini">
        <vxe-form-item title="名称" field="name">
          <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname">
          <vxe-input v-model="formData1.nickname" placeholder="请输入昵称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex">
          <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
            <vxe-option value="1" label="女"></vxe-option>
            <vxe-option value="2" label="男"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item>
          <vxe-button type="submit" status="primary">超小尺寸</vxe-button>
        </vxe-form-item>
      </vxe-form>
    </p>

    <!-- <p>
      <vxe-form :data="formData2" @submit="searchEvent" @reset="resetEvent">
        <vxe-form-item title="名称" field="name" span="8">
          <vxe-input v-model="formData2.name" placeholder="请输入名称"></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname" span="8">
          <vxe-input v-model="formData2.nickname" placeholder="请输入昵称"></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex" span="8">
          <vxe-select v-model="formData2.sex" placeholder="请选择性别">
            <vxe-option value="1" label="女"></vxe-option>
            <vxe-option value="2" label="男"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item title="角色" field="role" span="8">
          <vxe-input v-model="formData2.role" placeholder="请输入角色"></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="年龄" field="age" span="8">
          <vxe-input v-model="formData2.age" type="number" placeholder="请输入年龄"></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="区域" field="region" span="8">
          <vxe-input v-model="formData2.region" placeholder="请输入区域"></vxe-input>
        </vxe-form-item>
        <vxe-form-item align="center" span="24">
          <vxe-button type="submit" status="primary">查询</vxe-button>
          <vxe-button type="reset">重置</vxe-button>
        </vxe-form-item>
      </vxe-form>
    </div> -->

    <p>
      <vxe-form ref="xForm" :data="formData3" :rules="formRules3" :loading="loading3" title-align="right" title-width="100" @submit="submitEvent3" @reset="resetEvent">
        <vxe-form-item title="名称" field="name" span="12">
          <template v-slot="scope">
            <vxe-input v-model="formData3.name" placeholder="请输入名称" clearable @input="$refs.xForm.updateStatus(scope)"></vxe-input>
          </template>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname" span="12">
          <template v-slot="scope">
            <vxe-input v-model="formData3.nickname" placeholder="请输入昵称" clearable @input="$refs.xForm.updateStatus(scope)"></vxe-input>
          </template>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex" span="12">
          <template v-slot="scope">
            <vxe-select v-model="formData3.sex" placeholder="请选择性别" clearable @change="$refs.xForm.updateStatus(scope)">
              <vxe-option value="1" label="女"></vxe-option>
              <vxe-option value="2" label="男"></vxe-option>
            </vxe-select>
          </template>
        </vxe-form-item>
        <vxe-form-item title="年龄" field="age" span="12">
          <vxe-input v-model="formData3.age" type="number" placeholder="请输入年龄" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="地址" field="address" span="24">
          <vxe-textarea v-model="formData3.address" placeholder="请输入地址" clearable></vxe-textarea>
        </vxe-form-item>
        <vxe-form-item align="center" span="24">
          <vxe-button type="submit" status="primary">提交</vxe-button>
          <vxe-button type="reset">重置</vxe-button>
        </vxe-form-item>
      </vxe-form>
    </p>

    <p>
      <vxe-form :data="formData4" title-align="right" title-width="100" @submit="searchEvent" @reset="resetEvent" title-colon>
        <vxe-form-item title="名称" field="name" span="8">
          <vxe-input v-model="formData4.name" placeholder="请输入名称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="昵称" field="nickname" span="8" :title-prefix="{ message: '请输入汉字！', icon: 'fa fa-exclamation-circle' }">
          <vxe-input v-model="formData4.nickname" placeholder="请输入昵称" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="性别" field="sex" span="8">
          <vxe-select v-model="formData4.sex" placeholder="请选择性别" clearable>
            <vxe-option value="1" label="女"></vxe-option>
            <vxe-option value="2" label="男"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item title="年龄" field="age" span="8" :title-prefix="{ message: '请输入数值！', icon: 'fa fa-info-circle' }">
          <vxe-input v-model="formData4.age" type="number" placeholder="请输入年龄" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="区域" field="region" span="8">
          <vxe-input v-model="formData2.region" placeholder="请输入区域" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="状态" field="status" span="8">
          <vxe-select v-model="formData4.status" placeholder="请选择状态" clearable>
            <vxe-option value="0" label="失败"></vxe-option>
            <vxe-option value="1" label="成功"></vxe-option>
          </vxe-select>
        </vxe-form-item>
        <vxe-form-item title="身高" field="height" span="8" folding>
          <vxe-input v-model="formData4.height" placeholder="请输入身高" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="体重" field="weight" span="8" folding>
          <vxe-input v-model="formData4.weight" placeholder="请输入体重" clearable></vxe-input>
        </vxe-form-item>
        <vxe-form-item title="是否单身" field="single" span="8" folding>
          <vxe-radio-group v-model="formData4.single">
            <vxe-radio label="1">是</vxe-radio>
            <vxe-radio label="0">否</vxe-radio>
          </vxe-radio-group>
        </vxe-form-item>
        <vxe-form-item align="center" span="24" collapse-node>
          <vxe-button type="submit" status="primary">查询</vxe-button>
          <vxe-button type="reset">重置</vxe-button>
        </vxe-form-item>
      </vxe-form>
    </p>

    <p class="demo-code">{{ $t('app.body.button.showCode') }}</p>

    <pre>
      <code class="html">{{ demoCodes[0] }}</code>
      <code class="javascript">{{ demoCodes[1] }}</code>
    </pre>
  </div>
</template>

<script>
import hljs from 'highlight.js'

export default {
  data  () {
    return {
      formData1: {
        name: '',
        nickname: '',
        sex: '1'
      },
      formData2: {
        name: '',
        nickname: '',
        sex: '0',
        role: '',
        age: 22,
        region: null
      },
      loading3: false,
      formData3: {
        name: '',
        nickname: '',
        sex: '',
        age: 26,
        address: null
      },
      formRules3: {
        name: [
          { required: true, message: '请输入名称' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符' }
        ],
        nickname: [
          { required: true, message: '请输入昵称' }
        ],
        sex: [
          { required: true, message: '请选择性别' }
        ]
      },
      formData4: {
        name: '',
        nickname: '',
        sex: '',
        age: 30,
        status: '1',
        region: null,
        height: '178',
        weight: null,
        single: '1'
      },
      demoCodes: [
        `
        <p>
          <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent">
            <vxe-form-item title="名称" field="name">
              <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="昵称" field="nickname">
              <vxe-input v-model="formData1.nickname" placeholder="请输入昵称"></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="性别" field="sex">
              <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
                <vxe-option value="1" label="女"></vxe-option>
                <vxe-option value="2" label="男"></vxe-option>
              </vxe-select>
            </vxe-form-item>
            <vxe-form-item>
              <vxe-button type="submit" status="primary">默认尺寸</vxe-button>
            </vxe-form-item>
          </vxe-form>
          <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent" size="medium">
            <vxe-form-item title="名称" field="name">
              <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="昵称" field="nickname">
              <vxe-input v-model="formData1.nickname" placeholder="请输入昵称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="性别" field="sex">
              <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
                <vxe-option value="1" label="女"></vxe-option>
                <vxe-option value="2" label="男"></vxe-option>
              </vxe-select>
            </vxe-form-item>
            <vxe-form-item>
              <vxe-button type="submit" status="primary">中等尺寸</vxe-button>
            </vxe-form-item>
          </vxe-form>
          <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent" size="small">
            <vxe-form-item title="名称" field="name">
              <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="昵称" field="nickname">
              <vxe-input v-model="formData1.nickname" placeholder="请输入昵称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="性别" field="sex">
              <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
                <vxe-option value="1" label="女"></vxe-option>
                <vxe-option value="2" label="男"></vxe-option>
              </vxe-select>
            </vxe-form-item>
            <vxe-form-item>
              <vxe-button type="submit" status="primary">小型尺寸</vxe-button>
            </vxe-form-item>
          </vxe-form>
          <vxe-form :data="formData1" @submit="searchEvent" @reset="resetEvent" size="mini">
            <vxe-form-item title="名称" field="name">
              <vxe-input v-model="formData1.name" placeholder="请输入名称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="昵称" field="nickname">
              <vxe-input v-model="formData1.nickname" placeholder="请输入昵称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="性别" field="sex">
              <vxe-select v-model="formData1.sex" placeholder="请选择性别" clearable>
                <vxe-option value="1" label="女"></vxe-option>
                <vxe-option value="2" label="男"></vxe-option>
              </vxe-select>
            </vxe-form-item>
            <vxe-form-item>
              <vxe-button type="submit" status="primary">超小尺寸</vxe-button>
            </vxe-form-item>
          </vxe-form>
        </p>

        <p>
          <vxe-form ref="xForm" :data="formData3" :rules="formRules3" :loading="loading3" title-align="right" title-width="100" @submit="submitEvent3" @reset="resetEvent">
            <vxe-form-item title="名称" field="name" span="12">
              <template v-slot="scope">
                <vxe-input v-model="formData3.name" placeholder="请输入名称" clearable @input="$refs.xForm.updateStatus(scope)"></vxe-input>
              </template>
            </vxe-form-item>
            <vxe-form-item title="昵称" field="nickname" span="12">
              <template v-slot="scope">
                <vxe-input v-model="formData3.nickname" placeholder="请输入昵称" clearable @input="$refs.xForm.updateStatus(scope)"></vxe-input>
              </template>
            </vxe-form-item>
            <vxe-form-item title="性别" field="sex" span="12">
              <template v-slot="scope">
                <vxe-select v-model="formData3.sex" placeholder="请选择性别" clearable @change="$refs.xForm.updateStatus(scope)">
                  <vxe-option value="1" label="女"></vxe-option>
                  <vxe-option value="2" label="男"></vxe-option>
                </vxe-select>
              </template>
            </vxe-form-item>
            <vxe-form-item title="年龄" field="age" span="12">
              <vxe-input v-model="formData3.age" type="number" placeholder="请输入年龄" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="地址" field="address" span="24">
              <vxe-textarea v-model="formData3.address" placeholder="请输入地址" clearable></vxe-textarea>
            </vxe-form-item>
            <vxe-form-item align="center" span="24">
              <vxe-button type="submit" status="primary">提交</vxe-button>
              <vxe-button type="reset">重置</vxe-button>
            </vxe-form-item>
          </vxe-form>
        </p>

        <p>
          <vxe-form :data="formData4" title-align="right" title-width="100" @submit="searchEvent" @reset="resetEvent" title-colon>
            <vxe-form-item title="名称" field="name" span="8">
              <vxe-input v-model="formData4.name" placeholder="请输入名称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="昵称" field="nickname" span="8" :title-prefix="{ message: '请输入汉字！', icon: 'fa fa-exclamation-circle' }">
              <vxe-input v-model="formData4.nickname" placeholder="请输入昵称" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="性别" field="sex" span="8">
              <vxe-select v-model="formData4.sex" placeholder="请选择性别" clearable>
                <vxe-option value="1" label="女"></vxe-option>
                <vxe-option value="2" label="男"></vxe-option>
              </vxe-select>
            </vxe-form-item>
            <vxe-form-item title="年龄" field="age" span="8" :title-prefix="{ message: '请输入数值！', icon: 'fa fa-info-circle' }">
              <vxe-input v-model="formData4.age" type="number" placeholder="请输入年龄" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="区域" field="region" span="8">
              <vxe-input v-model="formData2.region" placeholder="请输入区域" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="状态" field="status" span="8">
              <vxe-select v-model="formData4.status" placeholder="请选择状态" clearable>
                <vxe-option value="0" label="失败"></vxe-option>
                <vxe-option value="1" label="成功"></vxe-option>
              </vxe-select>
            </vxe-form-item>
            <vxe-form-item title="身高" field="height" span="8" folding>
              <vxe-input v-model="formData4.height" placeholder="请输入身高" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="体重" field="weight" span="8" folding>
              <vxe-input v-model="formData4.weight" placeholder="请输入体重" clearable></vxe-input>
            </vxe-form-item>
            <vxe-form-item title="是否单身" field="single" span="8" folding>
              <vxe-radio-group v-model="formData4.single">
                <vxe-radio label="1">是</vxe-radio>
                <vxe-radio label="0">否</vxe-radio>
              </vxe-radio-group>
            </vxe-form-item>
            <vxe-form-item align="center" span="24" collapse-node>
              <vxe-button type="submit" status="primary">查询</vxe-button>
              <vxe-button type="reset">重置</vxe-button>
            </vxe-form-item>
          </vxe-form>
        </p>
        `,
        `
        export default {
          data () {
            return {
              formData1: {
                name: '',
                nickname: '',
                sex: '1'
              },
              loading3: false,
              formData3: {
                name: '',
                nickname: '',
                sex: '',
                age: 26,
                address: null
              },
              formRules3: {
                name: [
                  { required: true, message: '请输入名称' },
                  { min: 3, max: 5, message: '长度在 3 到 5 个字符' }
                ],
                nickname: [
                  { required: true, message: '请输入昵称' }
                ],
                sex: [
                  { required: true, message: '请选择性别' }
                ]
              },
              formData4: {
                name: '',
                nickname: '',
                sex: '',
                age: 30,
                status: '1',
                region: null,
                height: '178',
                weight: null,
                single: '1'
            }
          },
          methods: {
            submitEvent3 () {
              this.loading3 = true
              setTimeout(() => {
                this.loading3 = false
                this.$XModal.message({ message: '保存成功', status: 'success' })
              }, 1000)
            },
            searchEvent () {
              this.$XModal.message({ message: '查询事件', status: 'info' })
            },
            resetEvent () {
              this.$XModal.message({ message: '重置事件', status: 'info' })
            }
          }
        }
        `
      ]
    }
  },
  mounted () {
    Array.from(this.$el.querySelectorAll('pre code')).forEach((block) => {
      hljs.highlightBlock(block)
    })
  },
  methods: {
    submitEvent3 () {
      this.loading3 = true
      setTimeout(() => {
        this.loading3 = false
        this.$XModal.message({ message: '保存成功', status: 'success' })
      }, 1000)
    },
    searchEvent () {
      this.$XModal.message({ message: '查询事件', status: 'info' })
    },
    resetEvent () {
      this.$XModal.message({ message: '重置事件', status: 'info' })
    }
  }
}
</script>
