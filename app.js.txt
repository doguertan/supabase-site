import { createClient } from "https://cdn.jsdelivr.net/npm/@supabase/supabase-js/+esm";

const supabaseUrl = "BURAYA_URL";https://uayvmrbyrfeiitumahfl.supabase.co
const supabaseKey = "BURAYA_ANON_KEY";sb_publishable_z1kbZREUhhc5YyQFSVXWlQ_fF7f_pF6

const supabase = createClient(supabaseUrl, supabaseKey);

window.register = async function () {
  let email = document.getElementById("email").value;
  let password = document.getElementById("password").value;

  let { data, error } = await supabase.auth.signUp({
    email,
    password
  });

  document.getElementById("status").innerText =
    error ? error.message : "Kayıt başarılı!";
};

window.login = async function () {
  let email = document.getElementById("email").value;
  let password = document.getElementById("password").value;

  let { data, error } = await supabase.auth.signInWithPassword({
    email,
    password
  });

  document.getElementById("status").innerText =
    error ? error.message : "Giriş başarılı!";
};