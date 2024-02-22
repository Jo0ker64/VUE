<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    async login() {
      try {
        const response = await this.$axios.post("http://localhost:3000/api/login", {
          username: this.username,
          password: this.password,
        });

        // Stockez le token côté client (par exemple, utilisez Vuex ou localStorage)
        // Redirigez l'utilisateur vers la page de tableau de bord
        this.$router.push("/dashboard");
      } catch (error) {
        console.error("Login error:", error.message);
      }
    },
  },
};
</script>
