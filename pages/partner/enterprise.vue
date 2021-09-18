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
              label="사업체명"
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
            <span>{{ partners.length }}</span>개 업체가 조회되었습니다
          </span>
        </div>
        <div>
          <div
            v-if="partners == null || partners.length <= 0"
            class="text-center"
            style="height:500px;line-height:500px;"
          >
            <span style="vertical-align: middle;">업체가 존재하지 않습니다</span>
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
                <col width="10%">
                <col width="10%">
                <col width="10%">
                <col width="20%">
                <col width="10%">
              </colgroup>
              <thead>
                <tr>
                  <th>
                    카테고리
                  </th>
                  <th>
                    사업체
                  </th>
                  <th>
                    사업자등록번호
                  </th>
                  <th>
                    담당자
                  </th>
                  <th>
                    담당부서
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
                    {{ partner.businessNum }}
                  </td>
                  <td>
                    {{ partner.managerNm }}
                  </td>
                  <td>
                    {{ partner.managerDeptNm }}
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
      { name: '(주)황프로', businessNum: '123-45-78901' }
    ]
  }),
  methods: {
  }
}
</script>
