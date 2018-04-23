### <a name="a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a><span data-ttu-id="4bb2c-101">NetDataContractSerializer で .NET 4.5 でシリアル化 ConcurrentDictionary は .NET 4.5.1 または 4.5.2 で逆シリアル化することはできません。</span><span class="sxs-lookup"><span data-stu-id="4bb2c-101">A ConcurrentDictionary serialized in .NET 4.5 with NetDataContractSerializer cannot be deserialized by .NET 4.5.1 or 4.5.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4bb2c-102">説明</span><span class="sxs-lookup"><span data-stu-id="4bb2c-102">Details</span></span>|<span data-ttu-id="4bb2c-103">内部変更の種類ににより<xref:System.Collections.Concurrent.ConcurrentDictionary%602>.NET Framework 4.5 でシリアル化されるオブジェクトを使用して、 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> .NET Framework 4.5.1 または .NET Framework 4.5.2.Note で逆シリアル化することはできません、他の方向 (内を移動.NET Framework でのシリアル化 4.5.x と .NET Framework 4.5 で逆シリアル化) は動作します。</span><span class="sxs-lookup"><span data-stu-id="4bb2c-103">Due to internal changes to the type, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objects that are serialized with the .NET Framework 4.5 using the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> cannot be deserialized in the .NET Framework 4.5.1 or in the .NET Framework 4.5.2.Note that moving in the other direction (serializing with the .NET Framework 4.5.x and deserializing with the .NET Framework 4.5) works.</span></span> <span data-ttu-id="4bb2c-104">同様に、すべて 4.x バージョン間のシリアル化は、.NET Framework 4.6.Serializing と連携し、.NET Framework の 1 つのバージョンで逆シリアル化が影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="4bb2c-104">Similarly, all 4.x cross-version serialization works with the .NET Framework 4.6.Serializing and deserializing with a single version of the .NET Framework is not affected.</span></span>|
|<span data-ttu-id="4bb2c-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4bb2c-105">Suggestion</span></span>|<span data-ttu-id="4bb2c-106">シリアル化および逆シリアル化する必要がある場合、 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> 、.NET Framework 4.5 と .NET Framework 4.5.1/4.5.2 間、代替のシリアライザーと同様に、<xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name>または<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name>の代わりに、シリアライザーを使用する必要があります、<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>です。代わりに、この問題が .NET Framework 4.6 でアドレス指定されるため、.NET Framework のバージョンにアップグレードすることで解決可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bb2c-106">If it is necessary to serialize and deserialize a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> between the .NET Framework 4.5 and .NET Framework 4.5.1/4.5.2, an alternate serializer like the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> serializer should be used instead of the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>.Alternatively, because this issue is addressed in the .NET Framework 4.6, it may be solved by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="4bb2c-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="4bb2c-107">Scope</span></span>|<span data-ttu-id="4bb2c-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="4bb2c-108">Minor</span></span>|
|<span data-ttu-id="4bb2c-109">Version</span><span class="sxs-lookup"><span data-stu-id="4bb2c-109">Version</span></span>|<span data-ttu-id="4bb2c-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4bb2c-110">4.5.1</span></span>|
|<span data-ttu-id="4bb2c-111">型</span><span class="sxs-lookup"><span data-stu-id="4bb2c-111">Type</span></span>|<span data-ttu-id="4bb2c-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4bb2c-112">Runtime</span></span>|
