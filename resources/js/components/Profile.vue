<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12 mt-3">
        <div class="card card-widget widget-user">
          <!-- Add the bg color to the header using any of the bg-* classes -->
          <div
            class="widget-user-header text-white"
            style="background-image: url('./img/helsinki.jpg')"
          >
            <h3 class="widget-user-username text-right">Elizabeth Pierce</h3>
            <h5 class="widget-user-desc text-right">Web Designer</h5>
          </div>
          <div class="widget-user-image">
            <img class="img-circle" src="" alt="User Avatar" />
          </div>
          <div class="card-footer">
            <div class="row">
              <div class="col-sm-4 border-right">
                <div class="description-block">
                  <h5 class="description-header">3,200</h5>
                  <span class="description-text">SALES</span>
                </div>
                <!-- /.description-block -->
              </div>
              <!-- /.col -->
              <div class="col-sm-4 border-right">
                <div class="description-block">
                  <h5 class="description-header">13,000</h5>
                  <span class="description-text">FOLLOWERS</span>
                </div>
                <!-- /.description-block -->
              </div>
              <!-- /.col -->
              <div class="col-sm-4">
                <div class="description-block">
                  <h5 class="description-header">35</h5>
                  <span class="description-text">PRODUCTS</span>
                </div>
                <!-- /.description-block -->
              </div>
              <!-- /.col -->
            </div>
            <!-- /.row -->
          </div>
        </div>

        <!-- User info -->
        <div class="card">
          <div class="card-header p-2">
            <ul class="nav nav-pills">
              <li class="nav-item">
                <a class="nav-link active" href="#activity" data-toggle="tab"
                  >Activity</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#timeline" data-toggle="tab"
                  >Timeline</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#settings" data-toggle="tab"
                  >Settings</a
                >
              </li>
            </ul>
          </div>
          <!-- /.card-header -->
          <div class="card-body">
            <div class="tab-content">
              <div class="active tab-pane" id="activity"></div>

              <div class="tab-pane" id="settings">
                <form class="form-horizontal">
                  <div class="form-group row">
                    <label for="inputName" class="col-sm-10 col-form-label"
                      >Name</label
                    >
                    <div class="col-sm-10">
                      <input
                        type="email"
                        v-model="form.name"
                        class="form-control"
                        id="inputName"
                        placeholder="Name"
                      />
                    </div>
                  </div>
                  <div class="form-group row">
                    <label for="inputEmail" class="col-sm-10 col-form-label"
                      >Email</label
                    >
                    <div class="col-sm-10">
                      <input
                        type="email"
                        v-model="form.email"
                        class="form-control"
                        id="inputEmail"
                        placeholder="Email"
                      />
                    </div>
                  </div>
                  <div class="form-group row">
                    <label for="inputExperience" class="col-sm-10 col-form-label"
                      >Experience</label
                    >
                    <div class="col-sm-10">
                      <textarea
                        class="form-control"
                        id="inputExperience"
                        placeholder="Experience"
                      ></textarea>
                    </div>
                  </div>
                  <div class="form-group row">
                    <label for="inputPassword" class="col-sm-10 col-form-label"
                      >Password (leave empty if not changing)</label
                    >
                    <div class="col-sm-10">
                      <input
                        type="password"
                        class="form-control"
                        id="inputPassword"
                        placeholder="Password"
                      />
                    </div>
                  </div>
                  <div class="form-group row">
                    <div class="offset-sm-2 col-sm-10"></div>
                  </div>
                  <div class="form-group row">
                    <div class="offset-sm-2 col-sm-10">
                      <button type="submit" class="btn btn-success">
                        Update
                      </button>
                    </div>
                  </div>
                </form>
              </div>
              <!-- /.tab-pane -->
            </div>
            <!-- /.tab-content -->
          </div>
          <!-- /.card-body -->
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.widget-user-header {
  background-position: center center;
  background-size: cover;
}
</style>

<script>
import Form from "vform";

export default {
  data() {
    return {
      form: new Form({
        id:'',
        name: '',
        email:'',
        password:'',
        type:'',
        photo:''
      }),
    };
  },
  created() {
    axios.get("api/profile")
    .then(({ data }) => (this.form.fill(data)));
  },
};
</script>
