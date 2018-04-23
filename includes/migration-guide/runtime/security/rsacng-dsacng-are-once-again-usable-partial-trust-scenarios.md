### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a><span data-ttu-id="0d646-101">RSACng と DSACng がもう一度部分信頼シナリオでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0d646-101">RSACng and DSACng are once again usable in Partial Trust scenarios</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0d646-102">説明</span><span class="sxs-lookup"><span data-stu-id="0d646-102">Details</span></span>|<span data-ttu-id="0d646-103">CngLightup (いくつかの上位レベルの暗号化で使用される api など<xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) と<xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>場合によっては、完全な信頼に依存します。</span><span class="sxs-lookup"><span data-stu-id="0d646-103">CngLightup (used in several higher-level crypto apis, such as <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) and <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> in some cases rely on full trust.</span></span> <span data-ttu-id="0d646-104">アサートせず P/invoke が含まれます<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>権限、およびコード パスで<xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType>の需要のアクセス許可を持つ<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="0d646-104">These include P/Invokes without asserting <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> permissions, and code paths where <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> has permission demands for <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0d646-105">.NET Framework 4.6.2 から始めて、CngLightup に切り替えるには使用された<xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>可能な限りです。</span><span class="sxs-lookup"><span data-stu-id="0d646-105">Starting with the .NET Framework 4.6.2, CngLightup was used to switch to <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wherever possible.</span></span> <span data-ttu-id="0d646-106">その結果、部分信頼アプリケーションを正常に使用された<xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>が失敗し、スローを開始した<xref:System.Security.SecurityException>例外。この変更は、CngLightup を使用してすべての機能が必要なアクセス許可を持っているので、必要なアサートを追加します。</span><span class="sxs-lookup"><span data-stu-id="0d646-106">As a result, partial trust apps that successfully used <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> began to fail and throw <xref:System.Security.SecurityException> exceptions.This change adds the required asserts so that all functions using CngLightup have the required permissions.</span></span>|
|<span data-ttu-id="0d646-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0d646-107">Suggestion</span></span>|<span data-ttu-id="0d646-108">.NET Framework 4.6.2 でこの変更には、部分信頼アプリケーションが悪影響を場合は、.NET Framework 4.7.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0d646-108">If this change in the .NET Framework 4.6.2 has negatively impacted your partial trust apps, upgrade to the .NET Framework 4.7.1.</span></span>|
|<span data-ttu-id="0d646-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="0d646-109">Scope</span></span>|<span data-ttu-id="0d646-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="0d646-110">Edge</span></span>|
|<span data-ttu-id="0d646-111">Version</span><span class="sxs-lookup"><span data-stu-id="0d646-111">Version</span></span>|<span data-ttu-id="0d646-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0d646-112">4.6.2</span></span>|
|<span data-ttu-id="0d646-113">型</span><span class="sxs-lookup"><span data-stu-id="0d646-113">Type</span></span>|<span data-ttu-id="0d646-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0d646-114">Runtime</span></span>|
|<span data-ttu-id="0d646-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0d646-115">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
