<script>
  import { createEventDispatcher } from "svelte";
  export let text: string;
  const dispatch = createEventDispatcher();

  const onCopy = () => dispatch("copy", text);
  const onFail = (e) => dispatch("fail", e);

  const copy = () => {
    navigator.clipboard.writeText(text).then(onCopy, onFail);
  };
</script>

<slot {copy} />
