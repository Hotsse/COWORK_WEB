<template>
  <div>
    <v-card>
      <v-card-text>
        <v-row>
          <v-col
            cols="3"
          >
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
            <span>{{ partners.length }}</span>명이 조회되었습니다
          </span>
        </div>
        <div>
          <div
            v-if="partners == null || partners.length <= 0"
            class="text-center"
            style="height:500px;line-height:500px;"
          >
            <span style="vertical-align: middle;">결과가 존재하지 않습니다</span>
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
                <col width="10%">
                <col width="10%">
                <col width="50%">
                <col width="10%">
              </colgroup>
              <thead>
                <tr>
                  <th>
                    카테고리
                  </th>
                  <th>
                    개인명
                  </th>
                  <th>
                    이메일
                  </th>
                  <th>
                    연락처
                  </th>
                  <th>
                    작업
                  </th>
                  <th>
                    대표평점
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr
                  v-for="(partner, i) in partners"
                  :key="i"
                >
                  <td>
                    {{ partner.category }}
                  </td>
                  <td>
                    {{ partner.name }}
                  </td>
                  <td>
                    {{ partner.email }}
                  </td>
                  <td>
                    {{ partner.tel }}
                  </td>
                  <td>
                    {{ partner.workNm }}
                  </td>
                  <td>
                    {{ partner.eval }}
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
    partners: [
      { name: '홍길동', tel: '010-1234-5678' },
      { name: '김넥슨', tel: '010-2345-6789' }
    ]
  }),
  methods: {
  }
}
</script>
