<template>
    <Header/>
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
                            <li class="breadcrumb-item"><a href="#"><i class="feather icon-home"></i></a></li>
                            <li class="breadcrumb-item"><a href="#!">add artist</a></li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <!-- [ breadcrumb ] end -->

    <div class="row">
            <div class="col-sm-12">
                <div class="card">
                    <div class="card-header">
                        <h5>Artist information</h5>
                    </div>
                    <div class="card-body">
                        <form method="post" @submit.prevent="pushData">
                            <div class="row">
                                <div class="col-sm-6">
                                    <div class="form-group fill">
                                        <label class="floating-label" for="fname">First Name</label>
                                        <input type="text" class="form-control" id="fname" v-model="fname" required>
                                    </div>
                                </div>
                                <div class="col-sm-6">
                                    <div class="form-group">
                                        <label class="floating-label" for="lname">Last Name</label>
                                        <input type="text" class="form-control" id="lname" v-model="lname" required>
                                    </div>
                                </div>
                                <div class="form-group col-sm-6">
                                        <select class="form-control" id="exampleFormControlSelect1" v-model="gender" required>
                                            <option>Male</option>
                                            <option>Female</option>
                                        </select>
                                </div>
                                <div class="col-sm-6">
                                    <div class="form-group">
                                        <label class="floating-label" for="weburl">BirthDay</label>
                                        <input type="text" name="birthday" class="form-control" v-model="bday" required>
                                    </div>
                                </div>
                                <div class="col-sm-6">
                                    <div class="form-group">
                                        <label class="floating-label" for="weburl">Website Url</label>
                                        <input type="url" class="form-control" id="weburl" v-model="websiteurl" required>
                                    </div>
                                </div>
                                <div class="col-sm-6">
                                    <div class="form-group">
                                        <label class="floating-label" for="email">Email Address</label>
                                        <input type="email" class="form-control" id="email" v-model="emailid" required>
                                    </div>
                                </div>
                                <div class="col-sm-6">
                                <div class="form-group">
                                        <label for="biography">Biography</label>
                                        <textarea class="form-control" id="biography" rows="3" placeholder="tell me more about it" v-model="bio" required></textarea>
                                </div>
                                </div>
                                <div class="col-sm-6">
                                <div class="form-group">
                                        <label for="awards">Awards</label>
                                        <textarea class="form-control" id="awards" rows="3" placeholder="Any Awards " v-model="awards" required></textarea>
                                </div>
                                </div>
                                    <div class="col-sm-3">
                                        <h6>Genre</h6>
                                        <select
                                        class="js-example-basic-multiple col-sm-12"
                                        v-model="genre"
                                        multiple
                                        required
                                        >
                                        <option>pop</option>
                                        <option>rock</option>
                                        <option>jazz</option>
                                        </select>
                                    </div>
                                    <div class="col-sm-3">
                                        <h6>Profession</h6>
                                        <select
                                        class="js-example-basic-multiple col-sm-12"
                                        v-model="profession"
                                        multiple="multiple"
                                        required
                                        >
                                        <option>Artist</option>
                                        <option>Composer</option>
                                        <option>Song Writer</option>
                                        </select>
                                    </div>
                                    <div class="col-sm-3">
                                        <h6>Label</h6>
                                        <select
                                        class="js-example-basic-multiple col-sm-12"
                                        v-model="label"
                                        multiple="multiple"
                                        required
                                        >
                                        <option>label1</option>
                                        <option>label2</option>
                                        <option>label3</option>
                                        </select>
                                    </div>
                                    <div class="col-sm-3">
                                        <h6>Tags</h6>
                                        <select
                                        class="js-example-basic-multiple col-sm-12"
                                        v-model="tags"
                                        multiple="multiple"
                                        required
                                        >
                                        <option>tag1</option>
                                        <option>tag2</option>
                                        <option>tag3</option>
                                        </select>
                                    </div>
                                    <div class="input-group mb-3">
                                    <div class="input-group-prepend">
                                        <span class="input-group-text">Profile</span>
                                    </div>
                                    <div class="custom-file">
                                        <input
                                        type="file"
                                        class="custom-file-input"
                                        @change="handleFile"
                                        id="inputGroupFile01"
                                        required
                                        />
                                        <label class="custom-file-label" for="inputGroupFile01"
                                        >Choose Profile Picture</label
                                        >
                                    </div>
                                    </div>
                                    <button type="submit" class="btn btn-primary col-sm-12">
                                        Save
                                        </button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
    </div>
<!-- custom for adding something -->
<button hidden id="succeed" type="button" class="btn btn-success sweet-success has-ripple">Artist Added To Database<span class="ripple ripple-animate" style="height: 90.8281px; width: 90.8281px; animation-duration: 0.7s; animation-timing-function: linear; background: rgb(255, 255, 255); opacity: 0.4; top: -20.4063px; left: 3.20313px;"></span></button>
<button hidden id="formerros" type="button" class="btn btn-danger sweet-error has-ripple">Error<span class="ripple ripple-animate" style="height: 73.3906px; width: 73.3906px; animation-duration: 0.7s; animation-timing-function: linear; background: rgb(255, 255, 255); opacity: 0.4; top: -10.6875px; left: -22.0469px;"></span></button>
</template>

<script>
import Header from '../components/Header'
import { getApi } from '../axios-api.js'
export default {
  components: {
    Header
  },
  data () {
    return {
      fname: '',
      lname: '',
      bday: '05/05/1996',
      gender: 'Male',
      emailid: '',
      bio: '',
      profileimg: null,
      awards: '',
      websiteurl: '',
      genre: ['pop'],
      profession: 'artist',
      tags: 'tag1',
      label: 'label1'
    }
  },
  methods: {
    success () {
      console.log('suceess')
    },
    handleFile (event) {
      this.profileimg = event.target.files[0]
      console.log(event.target.files[0])
    },
    pushData () {
      const formData = new FormData()
      formData.append('fname', this.fname)
      formData.append('lname', this.lname)
      formData.append('bday', this.bday)
      formData.append('emailid', this.emailid)
      formData.append('gender', this.gender)
      formData.append('bio', this.bio)
      formData.append('profileimg', this.profileimg)
      formData.append('awards', this.awards)
      formData.append('websiteurl', this.websiteurl)
      formData.append('genre', this.genre)
      formData.append('profession', this.profession)
      formData.append('tags', this.tags)
      formData.append('label', this.label)
      getApi.post('/createartist',
        formData,
        {
          headers: {
            'Content-Type': 'multipart/form-data'
          }
        }
      ).then(res => {
        const succeed = document.getElementById('succeed')
        succeed.click()
      })
        .catch(error => {
          console.log({
            error,
            'error response': error.response
          })
          const ozz = document.getElementById('formerros')
          ozz.click()
        })
      // .catch(err => {
      //   console.log('Response body', err.response.data),
      //   function () {
      //     const ozz = document.getElementById('formerros')
      //     ozz.click()
      //   }
      // }
      // )
    }
  }
}
</script>
