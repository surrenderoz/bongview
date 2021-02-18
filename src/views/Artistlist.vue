<template>
  <Header />
  <div class="pcoded-main-container">
    <div class="pcoded-content">
      <!-- [ breadcrumb ] start -->
      <div class="page-header">
        <div class="page-block">
          <div class="row align-items-center">
            <div class="col-md-12">
              <div class="page-header-title">
                <h5 class="m-b-10">Artist Manager</h5>
              </div>
              <ul class="breadcrumb">
                <li class="breadcrumb-item">
                  <a href="#"><i class="feather icon-home"></i></a>
                </li>
                <li class="breadcrumb-item"><a href="#!">artists</a></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <!-- [ breadcrumb ] end -->
      <div class="row">
        <div class="col-lg-12">
          <div class="card user-profile-list">
            <div class="card-body">
              <div class="dt-responsive table-responsive">
                <table id="user-list-table" class="table nowrap">
                  <thead>
                    <tr>
                      <th>Name</th>
                      <th>Website</th>
                      <th>Genre</th>
                      <th>Label</th>
                      <th>Creaed date</th>
                      <th>Status</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr v-for='(data, index) in artists'
                    :key="index"
                    >
                      <td>
                        <div class="d-inline-block align-middle">
                          <img
                            :src="data.profileimg"
                            alt="user image"
                            class="img-radius align-top m-r-15"
                            style="width: 40px"
                          />
                          <div class="d-inline-block">
                            <h6 class="m-b-0">{{data.fname}}</h6>
                            <p class="m-b-0">{{data.emailid}}</p>
                          </div>
                        </div>
                      </td>
                      <td>{{data.websiteurl}}</td>
                      <td>{{data.genre}}</td>
                      <td>{{data.label}}</td>
                      <td>{{data.createdon}}</td>
                      <td>
                        <span class="badge badge-light-success">{{data.status}}</span>
                        <div class="overlay-edit">
                          <button type="button" class="btn btn-icon btn-success">
                            <i class="feather icon-check-circle"></i>
                          </button>
                          <button type="button" class="btn btn-icon btn-danger">
                            <i class="feather icon-trash-2"></i>
                          </button>
                        </div>
                      </td>
                    </tr>
                    <!-- <tr>
                      <td>
                        <div class="d-inline-block align-middle">
                          <img
                            src="assets/images/user/avatar-2.jpg"
                            alt="user image"
                            class="img-radius align-top m-r-15"
                            style="width: 40px"
                          />
                          <div class="d-inline-block">
                            <h6 class="m-b-0">Garrett Winters</h6>
                            <p class="m-b-0">gw@domain.com</p>
                          </div>
                        </div>
                      </td>
                      <td>Accountant</td>
                      <td>Tokyo</td>
                      <td>63</td>
                      <td>2011/07/25</td>
                      <td>
                        <span class="badge badge-light-danger">Disabled</span>
                        <div class="overlay-edit">
                          <button type="button" class="btn btn-icon btn-success">
                            <i class="feather icon-check-circle"></i>
                          </button>
                          <button type="button" class="btn btn-icon btn-danger">
                            <i class="feather icon-trash-2"></i>
                          </button>
                        </div>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <div class="d-inline-block align-middle">
                          <img
                            src="assets/images/user/avatar-3.jpg"
                            alt="user image"
                            class="img-radius align-top m-r-15"
                            style="width: 40px"
                          />
                          <div class="d-inline-block">
                            <h6 class="m-b-0">Ashton Cox</h6>
                            <p class="m-b-0">ac@domain.com</p>
                          </div>
                        </div>
                      </td>
                      <td>Junior Technical Author</td>
                      <td>San Francisco</td>
                      <td>66</td>
                      <td>2009/01/12</td>
                      <td>
                        <span class="badge badge-light-danger">Disabled</span>
                        <div class="overlay-edit">
                          <button type="button" class="btn btn-icon btn-success">
                            <i class="feather icon-check-circle"></i>
                          </button>
                          <button type="button" class="btn btn-icon btn-danger">
                            <i class="feather icon-trash-2"></i>
                          </button>
                        </div>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <div class="d-inline-block align-middle">
                          <img
                            src="assets/images/user/avatar-4.jpg"
                            alt="user image"
                            class="img-radius align-top m-r-15"
                            style="width: 40px"
                          />
                          <div class="d-inline-block">
                            <h6 class="m-b-0">Cedric Kelly</h6>
                            <p class="m-b-0">ck@domain.com</p>
                          </div>
                        </div>
                      </td>
                      <td>Senior Javascript Developer</td>
                      <td>Edinburgh</td>
                      <td>22</td>
                      <td>2012/03/29</td>
                      <td>
                        <span class="badge badge-light-success">Active</span>
                        <div class="overlay-edit">
                          <button type="button" class="btn btn-icon btn-success">
                            <i class="feather icon-check-circle"></i>
                          </button>
                          <button type="button" class="btn btn-icon btn-danger">
                            <i class="feather icon-trash-2"></i>
                          </button>
                        </div>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <div class="d-inline-block align-middle">
                          <img
                            src="assets/images/user/avatar-4.jpg"
                            alt="user image"
                            class="img-radius align-top m-r-15"
                            style="width: 40px"
                          />
                          <div class="d-inline-block">
                            <h6 class="m-b-0">Airi Satou</h6>
                            <p class="m-b-0">as@domain.com</p>
                          </div>
                        </div>
                      </td>
                      <td>Accountant</td>
                      <td>Tokyo</td>
                      <td>33</td>
                      <td>2008/11/28</td>
                      <td>
                        <span class="badge badge-light-success">Active</span>
                        <div class="overlay-edit">
                          <button type="button" class="btn btn-icon btn-success">
                            <i class="feather icon-check-circle"></i>
                          </button>
                          <button type="button" class="btn btn-icon btn-danger">
                            <i class="feather icon-trash-2"></i>
                          </button>
                        </div>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <div class="d-inline-block align-middle">
                          <img
                            src="assets/images/user/avatar-5.jpg"
                            alt="user image"
                            class="img-radius align-top m-r-15"
                            style="width: 40px"
                          />
                          <div class="d-inline-block">
                            <h6 class="m-b-0">Brielle Williamson</h6>
                            <p class="m-b-0">bw@domain.com</p>
                          </div>
                        </div>
                      </td>
                      <td>Integration Specialist</td>
                      <td>New York</td>
                      <td>61</td>
                      <td>2012/12/02</td>
                      <td>
                        <span class="badge badge-light-danger">Disabled</span>
                        <div class="overlay-edit">
                          <button type="button" class="btn btn-icon btn-success">
                            <i class="feather icon-check-circle"></i>
                          </button>
                          <button type="button" class="btn btn-icon btn-danger">
                            <i class="feather icon-trash-2"></i>
                          </button>
                        </div>
                      </td>
                    </tr> -->
                  </tbody>
                  <tfoot>
                    <tr>
                      <th>Name</th>
                      <th>Website</th>
                      <th>Genre</th>
                      <th>Label</th>
                      <th>Creaed date</th>
                      <th>Status</th>
                    </tr>
                  </tfoot>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '../components/Header'
import { getApi } from '../axios-api'
export default {
  components: {
    Header
  },
  data () {
    return {
      // fname: '',
      // lname: '',
      // bday: '',
      // gender: '',
      // emailid: '',
      // bio: '',
      // profileimg: null,
      // awards: '',
      // websiteurl: '',
      // genre: [],
      // rofession: '[]',
      // tags: [],
      // label: []
      artists: [],
      index: 0
    }
  },
  methods: {
    getArtist () {
      getApi.get('showartist')
        .then(response => {
          console.log(response.data)
          this.artists = response.data
        })
    }
  },
  beforeMount () {
    this.getArtist()
  },
  mounted () {
    // datatable Js
    const dataTables = document.createElement('script')
    const dataTables2 = document.createElement('script')
    const dataTables3 = document.createElement('script')
    dataTables.setAttribute('src', 'assets/js/plugins/jquery.dataTables.min.js')
    dataTables2.setAttribute('src', 'assets/js/plugins/dataTables.bootstrap4.min.js')
    dataTables3.setAttribute('src', 'assets/ozz.js')
    document.body.appendChild(dataTables)
    document.body.appendChild(dataTables2)
    document.body.appendChild(dataTables3)
  }
}
</script>
