<template>
  <div>
    <v-card>
      <v-card-text>
        <v-row>
          <v-col cols="1">
            카테고리
          </v-col>
          <v-col cols="5">
            체크박스 목록
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="1">
            조회조건
          </v-col>
          <v-col cols="4">
            <v-btn x-large color="primary">
              작업명
            </v-btn>
            <v-btn x-large>
              사업체명
            </v-btn>
            <v-btn x-large>
              담당자명
            </v-btn>
            <v-btn x-large>
              프로젝트명
            </v-btn>
          </v-col>
          <v-col cols="2">
            <v-text-field
              v-model="name"
              label="개인명"
              outlined
            />
          </v-col>
          <v-col
            cols="1"
          >
            <v-btn block x-large color="primary">
              조회
            </v-btn>
          </v-col>
          <v-col
            cols="1"
          >
            <v-btn block x-large>
              초기화
            </v-btn>
          </v-col>
        </v-row>
      </v-card-text>
    </v-card>
    <v-card>
      <v-card-text>
        <div>
          <span>
            <span>{{ products.length }}</span>개의 완성물이 조회되었습니다
          </span>
        </div>
        <div>
          <div
            v-if="products == null || products.length <= 0"
            class="text-center"
            style="height:500px;line-height:500px;"
          >
            <span style="vertical-align: middle;">완성물이 존재하지 않습니다</span>
          </div>
          <v-simple-table
            v-else
            fixed-header
            height="500px"
          >
            <template #default>
              <colgroup>
                <col width="10%">
                <col width="10%">
                <col width="40%">
                <col width="10%">
                <col width="10%">
                <col width="20%">
              </colgroup>
              <thead>
                <tr>
                  <th>
                    카테고리
                  </th>
                  <th>
                    프로젝트
                  </th>
                  <th>
                    작업
                  </th>
                  <th>
                    계약금액
                  </th>
                  <th>
                    작업기간
                  </th>
                  <th>
                    등록일시
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr
                  v-for="(product, i) in products"
                  :key="i"
                >
                  <td>
                    {{ product.category }}
                  </td>
                  <td>
                    {{ product.projectNm }}
                  </td>
                  <td>
                    {{ product.workNm }}
                  </td>
                  <td>
                    {{ product.contPay }}
                  </td>
                  <td>
                    -
                  </td>
                  <td>
                    {{ product.regDtt }}
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  components: {
  },
  data: () => ({
    products: [
      { category: 'BGM', projectNm: '테스트게임1', workNm: '테스트게임1 시즌4 에피소드4 레이드 전투 BGM', contPay: '1,980,000 원', regDtt: '2021-06-01 12:14' },
      { category: 'Effect', projectNm: '테스트게임2', workNm: '테스트게임2 이펙트', contPay: '2,400,000 원', regDtt: '2021-03-17 11:15' }
    ]
  }),
  methods: {
  }
}
</script>
