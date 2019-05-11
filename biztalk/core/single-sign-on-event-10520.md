---
title: シングル サインオン:イベント 10520 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91662072-d87c-4290-8afb-2143143ee858
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a711e7ef49d32b85d774438e4e9f42e9805a99a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400231"
---
# <a name="single-sign-on-event-10520"></a><span data-ttu-id="e0d0d-102">シングル サインオン:イベント 10520</span><span class="sxs-lookup"><span data-stu-id="e0d0d-102">Single Sign-On: Event 10520</span></span>
## <a name="details"></a><span data-ttu-id="e0d0d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e0d0d-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e0d0d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e0d0d-104">Product Name</span></span>   |                                                       <span data-ttu-id="e0d0d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e0d0d-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="e0d0d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e0d0d-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="e0d0d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e0d0d-107">Event ID</span></span>     |                                                                 <span data-ttu-id="e0d0d-108">10520</span><span class="sxs-lookup"><span data-stu-id="e0d0d-108">10520</span></span>                                                                  |
|  <span data-ttu-id="e0d0d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e0d0d-109">Event Source</span></span>   |                                                                 <span data-ttu-id="e0d0d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e0d0d-110">ENTSSO</span></span>                                                                 |
|    <span data-ttu-id="e0d0d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e0d0d-111">Component</span></span>    |                                                                  <span data-ttu-id="e0d0d-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="e0d0d-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="e0d0d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e0d0d-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="e0d0d-114">SSO_WARN_NO_SECRETS</span><span class="sxs-lookup"><span data-stu-id="e0d0d-114">SSO_WARN_NO_SECRETS</span></span>                                                           |
|  <span data-ttu-id="e0d0d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e0d0d-115">Message Text</span></span>   | <span data-ttu-id="e0d0d-116">マスター シークレット サーバーのレジストリでシークレットが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-116">No secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="e0d0d-117">生成するか、マスター シークレットを復元するには、構成ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-117">Use the configuration tools to generate or restore a master secret.</span></span> |

## <a name="explanation"></a><span data-ttu-id="e0d0d-118">説明</span><span class="sxs-lookup"><span data-stu-id="e0d0d-118">Explanation</span></span>  
 <span data-ttu-id="e0d0d-119">この警告イベントは、シークレットが見つからなかったこと、マスター シークレット サーバーのレジストリを示します。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-119">This Warning event indicates that no secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="e0d0d-120">SSO マスター シークレットは、SSO マスター シークレット サーバーのレジストリに暗号化されて格納されます。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-120">The SSO master secrets are stored encrypted in the registry of the SSO master secret server.</span></span> <span data-ttu-id="e0d0d-121">2 つのシークレットがレジストリに保持通常: 現在のマスター シークレットと以前のマスター シークレット。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-121">Two secrets are typically kept in the registry: the current master secret, and the previous master secret.</span></span> <span data-ttu-id="e0d0d-122">シークレットは、GUID (マスター シークレット id) を使用して識別されます。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-122">Secrets are identified using a GUID (the master secret id).</span></span> <span data-ttu-id="e0d0d-123">要求されたときに、レジストリで指定されたマスター シークレットが見つからない場合、このエラー コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-123">If the specified master secret cannot be found in the registry when requested, this error code will be returned.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e0d0d-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e0d0d-124">User Action</span></span>  
 <span data-ttu-id="e0d0d-125">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-125">To resolve this warnming, do one or more of the following:</span></span>  

- <span data-ttu-id="e0d0d-126">マスター シークレット サーバー名が正しく、想定どおりのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-126">Check that the master secret server name is correct and as expected.</span></span>  

- <span data-ttu-id="e0d0d-127">正しい場合は、マスター シークレットがマスター シークレット サーバーのレジストリに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-127">If it is correct, check that the master secret is present in the registry of that master secret server.</span></span> <span data-ttu-id="e0d0d-128">マスター シークレットは、hkey_local_machine \software\microsoft\entsso\ssoss にあります (このキーは、SSO マスター シークレット サーバー上にのみ存在) にあります。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-128">The master secret is located under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS (this key is present only on the SSO master secret server).</span></span>  

- <span data-ttu-id="e0d0d-129">このキーがない場合、マスター シークレットが存在しません。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-129">If that key is missing then the master secret is not present.</span></span> <span data-ttu-id="e0d0d-130">暗号化されたキーが含まれている Guid という名前の SSOSS の下に 1 つまたは複数のキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-130">There should be one or more keys under SSOSS named as GUIDs which contain the encrypted keys.</span></span> <span data-ttu-id="e0d0d-131">これらが存在しない場合、マスター シークレットが存在しません。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-131">If these are not present then the master secret is not present.</span></span> <span data-ttu-id="e0d0d-132">マスター シークレットは Guid (マスター シークレット id) で識別されるため、これらの Guid (存在する) 場合は要求されたシークレットのマスター シークレット id と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-132">Master secrets are identified with GUIDs (the master secret id) so these GUIDs (if present) should match the master secret id of the secret that was requested.</span></span> <span data-ttu-id="e0d0d-133">Guid という名前のキーがある場合、要求されたマスター シークレット id に一致しないが、レジストリにマスター シークレットと SSO データベース (SSODB) 内のデータの暗号化に使用されたシークレットも。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-133">If there are keys named as GUIDs but they don’t match the requested master secret id, then there is a mixup between the master secret in the registry and the secret that was used to encrypt the data in the SSO database (SSODB).</span></span> <span data-ttu-id="e0d0d-134">この場合、別のマスター シークレットを復元する必要があります。 または下位レベルのバックアップから SSODB が復元された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-134">It may be necessary to restore a different master secret in this case, or maybe the SSODB has been restored from a downlevel backup.</span></span> <span data-ttu-id="e0d0d-135">場合は、マスター シークレットがまったく存在しない、SSO 構成ツール (コマンドラインまたは MMC) を使用してバックアップを復元できますか、新しいシークレットを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-135">If the master secret is not present at all, then it can be restored form backup using the SSO configuration tools (command line or MMC) or a new secret can be generated.</span></span> <span data-ttu-id="e0d0d-136">通常どおりことに注意してくださいここでは新しいインストールがない場合は、新しいマスター シークレットを生成する場合のみ、SSO データベース内のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-136">Note that you would normally only want to generate a new master secret if this is a new installation and there is no existing encrypted data in the SSO database.</span></span> <span data-ttu-id="e0d0d-137">マスター シークレットは通常、初期構成中に最初に生成されます。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-137">The master secret is normally generated for the first time during initial configuration.</span></span>  

  <span data-ttu-id="e0d0d-138">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="e0d0d-138">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="e0d0d-139">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="e0d0d-139">Master Secret Server</span></span>](../core/master-secret-server.md)  

- [<span data-ttu-id="e0d0d-140">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="e0d0d-140">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  

- [<span data-ttu-id="e0d0d-141">SSO の構成</span><span class="sxs-lookup"><span data-stu-id="e0d0d-141">Configuring SSO</span></span>](../core/configuring-sso.md)
