### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a><span data-ttu-id="4cb0f-101">XmlSerializer がアクセス不可能のいずれかでアクセス可能なメンバーを非表示にする型をシリアル化中に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4cb0f-101">XmlSerializer fails while serializing a type that hides an accessible member with an inaccessible one</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4cb0f-102">説明</span><span class="sxs-lookup"><span data-stu-id="4cb0f-102">Details</span></span>|<span data-ttu-id="4cb0f-103">派生型をシリアル化するとき、<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>型にアクセスできないフィールドまたは非表示にする ('new' キーワード) を使用してフィールドまたはプロパティが既にアクセス可能な (パブリック、たとえば) ものと同じ名前の基本型のプロパティが含まれている場合に失敗することができます。</span><span class="sxs-lookup"><span data-stu-id="4cb0f-103">When serializing a derived type, the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> can fail if the type contains an inaccessible field or property that hides (via the 'new' keyword) a field or property of the same name that was previously accessible (public, for example) on the base type.</span></span>|
|<span data-ttu-id="4cb0f-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4cb0f-104">Suggestion</span></span>|<span data-ttu-id="4cb0f-105">新しい非表示のメンバーがアクセスできるようにするでこの問題を解決する、 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> (マークすることによって、パブリックなど)。また、次の構成設定が、4.0 に戻ります。 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 、問題が解決の動作。</span><span class="sxs-lookup"><span data-stu-id="4cb0f-105">This problem can be solved by making the new, hiding member accessible to the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> (by marking it public, for example).Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> behavior, which will fix the problem:</span></span><pre><code class="language-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="4cb0f-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="4cb0f-106">Scope</span></span>|<span data-ttu-id="4cb0f-107">マイナー</span><span class="sxs-lookup"><span data-stu-id="4cb0f-107">Minor</span></span>|
|<span data-ttu-id="4cb0f-108">Version</span><span class="sxs-lookup"><span data-stu-id="4cb0f-108">Version</span></span>|<span data-ttu-id="4cb0f-109">4.5</span><span class="sxs-lookup"><span data-stu-id="4cb0f-109">4.5</span></span>|
|<span data-ttu-id="4cb0f-110">型</span><span class="sxs-lookup"><span data-stu-id="4cb0f-110">Type</span></span>|<span data-ttu-id="4cb0f-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4cb0f-111">Runtime</span></span>|
|<span data-ttu-id="4cb0f-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4cb0f-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
