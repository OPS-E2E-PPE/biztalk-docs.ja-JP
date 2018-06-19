---
title: 'シングル サインオン: イベント 10520 |Microsoft ドキュメント'
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
ms.openlocfilehash: 9349452d99518f210237c5e8dd0f945d1f92aa46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271914"
---
# <a name="single-sign-on-event-10520"></a><span data-ttu-id="10f79-102">シングル サインオン: イベント 10520</span><span class="sxs-lookup"><span data-stu-id="10f79-102">Single Sign-On: Event 10520</span></span>
## <a name="details"></a><span data-ttu-id="10f79-103">詳細</span><span class="sxs-lookup"><span data-stu-id="10f79-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10f79-104">製品名</span><span class="sxs-lookup"><span data-stu-id="10f79-104">Product Name</span></span>|<span data-ttu-id="10f79-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="10f79-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="10f79-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="10f79-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="10f79-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="10f79-107">Event ID</span></span>|<span data-ttu-id="10f79-108">10520</span><span class="sxs-lookup"><span data-stu-id="10f79-108">10520</span></span>|  
|<span data-ttu-id="10f79-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="10f79-109">Event Source</span></span>|<span data-ttu-id="10f79-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="10f79-110">ENTSSO</span></span>|  
|<span data-ttu-id="10f79-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10f79-111">Component</span></span>|<span data-ttu-id="10f79-112">N\A</span><span class="sxs-lookup"><span data-stu-id="10f79-112">N\A</span></span>|  
|<span data-ttu-id="10f79-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="10f79-113">Symbolic Name</span></span>|<span data-ttu-id="10f79-114">SSO_WARN_NO_SECRETS</span><span class="sxs-lookup"><span data-stu-id="10f79-114">SSO_WARN_NO_SECRETS</span></span>|  
|<span data-ttu-id="10f79-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="10f79-115">Message Text</span></span>|<span data-ttu-id="10f79-116">マスター シークレット サーバーのレジストリでシークレットが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="10f79-116">No secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="10f79-117">構成ツールを使用して、マスター シークレットを生成または復元してください。</span><span class="sxs-lookup"><span data-stu-id="10f79-117">Use the configuration tools to generate or restore a master secret.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="10f79-118">説明</span><span class="sxs-lookup"><span data-stu-id="10f79-118">Explanation</span></span>  
 <span data-ttu-id="10f79-119">この警告イベントは、マスター シークレット サーバーのレジストリでシークレットが見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="10f79-119">This Warning event indicates that no secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="10f79-120">SSO マスター シークレットは、SSO マスター シークレット サーバーのレジストリに暗号化されて格納されます。</span><span class="sxs-lookup"><span data-stu-id="10f79-120">The SSO master secrets are stored encrypted in the registry of the SSO master secret server.</span></span> <span data-ttu-id="10f79-121">通常、現在のマスター シークレットと以前のマスター シークレットの 2 つのシークレットがレジストリに格納されています。</span><span class="sxs-lookup"><span data-stu-id="10f79-121">Two secrets are typically kept in the registry: the current master secret, and the previous master secret.</span></span> <span data-ttu-id="10f79-122">シークレットは、GUID (マスター シークレット ID) を使用して識別されます。</span><span class="sxs-lookup"><span data-stu-id="10f79-122">Secrets are identified using a GUID (the master secret id).</span></span> <span data-ttu-id="10f79-123">要求されたときに指定されたマスター シークレットがレジストリ内に見つからなかった場合、このエラー コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="10f79-123">If the specified master secret cannot be found in the registry when requested, this error code will be returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10f79-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="10f79-124">User Action</span></span>  
 <span data-ttu-id="10f79-125">この警告を解決するには、次のいずれかの操作 (あるいは複数の操作) を行います。</span><span class="sxs-lookup"><span data-stu-id="10f79-125">To resolve this warnming, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="10f79-126">マスター シークレット サーバー名が正しく、想定どおりであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10f79-126">Check that the master secret server name is correct and as expected.</span></span>  
  
-   <span data-ttu-id="10f79-127">マスター シークレット サーバー名が正しい場合は、マスター シークレットがマスター シークレット サーバーのレジストリ内に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="10f79-127">If it is correct, check that the master secret is present in the registry of that master secret server.</span></span> <span data-ttu-id="10f79-128">マスター シークレットは、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS にあります (このキーは SSO マスター シークレット サーバー上にのみ存在します)。</span><span class="sxs-lookup"><span data-stu-id="10f79-128">The master secret is located under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS (this key is present only on the SSO master secret server).</span></span>  
  
-   <span data-ttu-id="10f79-129">このキーがない場合、マスター シークレットは存在しません。</span><span class="sxs-lookup"><span data-stu-id="10f79-129">If that key is missing then the master secret is not present.</span></span> <span data-ttu-id="10f79-130">SSOSS の下に GUID という名前の 1 つまたは複数のキーに暗号化されたキーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="10f79-130">There should be one or more keys under SSOSS named as GUIDs which contain the encrypted keys.</span></span> <span data-ttu-id="10f79-131">これらのキーが存在しない場合、マスター シークレットは存在していません。</span><span class="sxs-lookup"><span data-stu-id="10f79-131">If these are not present then the master secret is not present.</span></span> <span data-ttu-id="10f79-132">マスター シークレットは GUID (マスター シークレット ID) によって識別されるので、これらの GUID (存在する場合) は要求されたシークレットのマスター シークレット ID と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="10f79-132">Master secrets are identified with GUIDs (the master secret id) so these GUIDs (if present) should match the master secret id of the secret that was requested.</span></span> <span data-ttu-id="10f79-133">GUID という名前のキーが存在していても、要求されたマスター シークレット ID と一致しない場合は、レジストリ内のマスター シークレットと、SSO データベース (SSODB) 内のデータを暗号化するために使用されたシークレットが混同されています。</span><span class="sxs-lookup"><span data-stu-id="10f79-133">If there are keys named as GUIDs but they don’t match the requested master secret id, then there is a mixup between the master secret in the registry and the secret that was used to encrypt the data in the SSO database (SSODB).</span></span> <span data-ttu-id="10f79-134">この場合は別のマスター シークレットを復元することが必要になる、つまり下位レベルのバックアップから SSODB が復元されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10f79-134">It may be necessary to restore a different master secret in this case, or maybe the SSODB has been restored from a downlevel backup.</span></span> <span data-ttu-id="10f79-135">マスター シークレットがまったく存在しない場合は、SSO 構成ツール (コマンド ラインまたは MMC) を使用してバックアップから復元するか、新しいシークレットを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="10f79-135">If the master secret is not present at all, then it can be restored form backup using the SSO configuration tools (command line or MMC) or a new secret can be generated.</span></span> <span data-ttu-id="10f79-136">これが新しいインストールであり、SSO データベース内に既存の暗号化されたデータが存在しない場合は、通常、新しいマスター シークレットを生成するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="10f79-136">Note that you would normally only want to generate a new master secret if this is a new installation and there is no existing encrypted data in the SSO database.</span></span> <span data-ttu-id="10f79-137">マスター シークレットは、通常、最初の構成を行うときに初めて生成されます。</span><span class="sxs-lookup"><span data-stu-id="10f79-137">The master secret is normally generated for the first time during initial configuration.</span></span>  
  
 <span data-ttu-id="10f79-138">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="10f79-138">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="10f79-139">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="10f79-139">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="10f79-140">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="10f79-140">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="10f79-141">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="10f79-141">Configuring SSO</span></span>](../core/configuring-sso.md)