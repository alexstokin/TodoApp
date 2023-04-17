<script>
    import { useForm, validators, HintGroup, Hint, email, required } from "svelte-use-form";
  
    export const form = useForm();
  </script>
  
  <form class="flex flex-col justify-between" use:form>
    <h1>Login</h1>
  
    <input class="mb-5" type="email" name="email" use:validators={[required, email]} />
    <HintGroup for="email">
      <Hint on="required">This is a mandatory field</Hint>
      <Hint on="email" hideWhenRequired>Email is not valid</Hint>
    </HintGroup>
  
    <input class="mb-5" type="password" name="password" use:validators={[required]} />
    <Hint for="password" on="required">This is a mandatory field</Hint>
  
    <button class="group flex items-center rounded-md border-cream-four bg-green-one px-6 py-3 text-lg font-semibold text-gray-five outline outline-2 outline-offset-2 outline-green-one hover:text-green-five focus-visible:text-green-five focus-visible:outline-green-five" disabled={!$form.valid}>Login</button> 
  </form>