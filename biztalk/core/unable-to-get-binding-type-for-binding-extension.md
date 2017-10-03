---
title: "バインド拡張機能のバインドの種類を取得できません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 453a579daae80a202df1ed4d3c72ae9c13f47d9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a><span data-ttu-id="877e3-102">バインド拡張機能のバインドの種類を取得できません</span><span class="sxs-lookup"><span data-stu-id="877e3-102">Unable to get binding type for binding extension</span></span>
## <a name="details"></a><span data-ttu-id="877e3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="877e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="877e3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="877e3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="877e3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="877e3-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="877e3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="877e3-106">Event ID</span></span>|<span data-ttu-id="877e3-107">0</span><span class="sxs-lookup"><span data-stu-id="877e3-107">0</span></span>|  
|<span data-ttu-id="877e3-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="877e3-108">Event Source</span></span>|<span data-ttu-id="877e3-109">0</span><span class="sxs-lookup"><span data-stu-id="877e3-109">0</span></span>|  
|<span data-ttu-id="877e3-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="877e3-110">Component</span></span>|<span data-ttu-id="877e3-111">0</span><span class="sxs-lookup"><span data-stu-id="877e3-111">0</span></span>|  
|<span data-ttu-id="877e3-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="877e3-112">Symbolic Name</span></span>|<span data-ttu-id="877e3-113">0</span><span class="sxs-lookup"><span data-stu-id="877e3-113">0</span></span>|  
|<span data-ttu-id="877e3-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="877e3-114">Message Text</span></span>|<span data-ttu-id="877e3-115">バインド拡張機能 "{0}" のバインドの種類を取得できません。</span><span class="sxs-lookup"><span data-stu-id="877e3-115">Unable to get binding type for binding extension "{0}".</span></span> <span data-ttu-id="877e3-116">アプリケーションが開いている状態のときに machine.config が更新された場合は、アプリケーションを再起動して変更を反映してください。</span><span class="sxs-lookup"><span data-stu-id="877e3-116">If machine.config was updated while your application was open, restart your application to pick up changes.</span></span> <span data-ttu-id="877e3-117">machine.config にこのバインド拡張機能が登録されているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="877e3-117">Verify the binding extension is registered in machine.config</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="877e3-118">説明</span><span class="sxs-lookup"><span data-stu-id="877e3-118">Explanation</span></span>  
 <span data-ttu-id="877e3-119">WCF-Custom または WCF-CustomIsolated トランスポートのカスタム バインディング拡張機能が適切に構成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="877e3-119">A custom binding extension for a WCF-Custom or a WCF-CustomIsolated transport was not configured properly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="877e3-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="877e3-120">User Action</span></span>  
 <span data-ttu-id="877e3-121">解決するのには、このエラーは、次の 1 つ以上を実行します。</span><span class="sxs-lookup"><span data-stu-id="877e3-121">To resolve this error do one or more of the following:</span></span>  
  
-   <span data-ttu-id="877e3-122">確認、 **machine.config ファイル**で**%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**が、 \< **bindingExtensions**> 要素適切に構成されています。</span><span class="sxs-lookup"><span data-stu-id="877e3-122">Ensure the **machine.config file** in **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** has the \<**bindingExtensions**> element configured properly.</span></span>  
  
-   <span data-ttu-id="877e3-123">Windows エクスプ ローラーに移動**%WinDir%\Assembly**、カスタム バインディングの拡張機能を実装するアセンブリが正しくインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="877e3-123">In Windows Explorer, go to **%WinDir%\Assembly**, and make sure the assemblies implementing the custom binding extension are installed properly.</span></span>  
  
-   <span data-ttu-id="877e3-124">WCF-Custom アダプターの場合、BizTalk 管理コンソールで、WCF トランスポートを実行するホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="877e3-124">For the WCF-Custom adapter, in the BizTalk Administration console, restart the host instance running the WCF transport.</span></span>  
  
-   <span data-ttu-id="877e3-125">WCF-CustomIsolated アダプターの場合、IIS 管理コンソールで、WCF トランスポートをホストするアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="877e3-125">For the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool hosting the WCF transport.</span></span>  
  
-   <span data-ttu-id="877e3-126">BizTalk 管理コンソールを開いていた場合は、閉じてから開きます</span><span class="sxs-lookup"><span data-stu-id="877e3-126">Open and close the BizTalk Administration console if it was opened</span></span>  
  
 <span data-ttu-id="877e3-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="877e3-127">For further information, see the following resource:</span></span>  
  
-   [<span data-ttu-id="877e3-128">WCF アダプターで WCF 機能拡張ポイントを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="877e3-128">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)