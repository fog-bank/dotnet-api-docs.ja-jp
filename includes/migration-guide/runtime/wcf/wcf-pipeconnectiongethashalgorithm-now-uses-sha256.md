### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="5cf9a-101">WCF PipeConnection.GetHashAlgorithm は SHA256 を使用するようになりました</span><span class="sxs-lookup"><span data-stu-id="5cf9a-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5cf9a-102">説明</span><span class="sxs-lookup"><span data-stu-id="5cf9a-102">Details</span></span>|<span data-ttu-id="5cf9a-103">以降、.NET Framework 4.7.1 では、Windows Communication Foundation は、名前付きパイプのランダムな名前を生成するのにには SHA256 ハッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="5cf9a-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="5cf9a-104">.NET Framework 4.7 と以前のバージョンでは、SHA1 ハッシュに使用します。</span><span class="sxs-lookup"><span data-stu-id="5cf9a-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="5cf9a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5cf9a-105">Suggestion</span></span>|<span data-ttu-id="5cf9a-106">.NET Framework 4.7.1 でこの変更に互換性の問題に実行するか、後ですることができますオプトアウトに次の行を追加することによって場合、 <code>&lt;runtime&gt;</code> app.config ファイルのセクション。</span><span class="sxs-lookup"><span data-stu-id="5cf9a-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="5cf9a-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="5cf9a-107">Scope</span></span>|<span data-ttu-id="5cf9a-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="5cf9a-108">Minor</span></span>|
|<span data-ttu-id="5cf9a-109">Version</span><span class="sxs-lookup"><span data-stu-id="5cf9a-109">Version</span></span>|<span data-ttu-id="5cf9a-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="5cf9a-110">4.7.1</span></span>|
|<span data-ttu-id="5cf9a-111">型</span><span class="sxs-lookup"><span data-stu-id="5cf9a-111">Type</span></span>|<span data-ttu-id="5cf9a-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="5cf9a-112">Runtime</span></span>|
