<script>
    import Landing from "../components/landing.svelte";
    import AboutSystem from "../components/aboutSystem.svelte";
    import PriceList from "../components/priceList.svelte";
    import Qna from "../components/basic/qna.svelte";
    import Review from "../components/review.svelte";
    import Contact from "../components/contact.svelte";
    import BubblesCta from "../components/small/bubblesCta.svelte";
    import Partners from "../components/basic/partners.svelte";
</script>
<Landing/>
<BubblesCta bigText="Proč zrovna MY?" smallText="Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod. Tempor invidunt ut labore et dolore magna aliquyam erat, sed" img="why-us" imgMarginRight="-3"/>
<AboutSystem/>
<PriceList/>
<Partners/>
<Qna/>
<BubblesCta bigText="Vaše zpětná vazba je pro nás důležitá" smallText="Zanechte nám hodnocení aby sme vědeli co máme zlepšit příště." img="review-cta" imgMarginRight="-8.5"/>
<Review/>
<Contact/>