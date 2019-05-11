---
title: 作成する受信場所のコマンドが失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f73ff211-af7f-40be-ad7e-7bde7bf75a2d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 559b2bee91cde68afa307de8d25fc89e4ceabcb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354272"
---
# <a name="create-receive-locations-command-failed"></a><span data-ttu-id="6263f-102">受信場所の作成コマンドが失敗しました</span><span class="sxs-lookup"><span data-stu-id="6263f-102">Create receive locations command failed</span></span>
## <a name="details"></a><span data-ttu-id="6263f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6263f-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6263f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6263f-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6263f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6263f-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6263f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6263f-106">Event ID</span></span>     |                                         <span data-ttu-id="6263f-107">0</span><span class="sxs-lookup"><span data-stu-id="6263f-107">0</span></span>                                          |
|  <span data-ttu-id="6263f-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6263f-108">Event Source</span></span>   |                                         <span data-ttu-id="6263f-109">0</span><span class="sxs-lookup"><span data-stu-id="6263f-109">0</span></span>                                          |
|    <span data-ttu-id="6263f-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6263f-110">Component</span></span>    |                                         <span data-ttu-id="6263f-111">0</span><span class="sxs-lookup"><span data-stu-id="6263f-111">0</span></span>                                          |
|  <span data-ttu-id="6263f-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6263f-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="6263f-113">0</span><span class="sxs-lookup"><span data-stu-id="6263f-113">0</span></span>                                          |
|  <span data-ttu-id="6263f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6263f-114">Message Text</span></span>   |  <span data-ttu-id="6263f-115">作成する受信場所のコマンドが失敗しました。ファイル名 ={0}引数 ={1} ExitCode ={2}</span><span class="sxs-lookup"><span data-stu-id="6263f-115">Create receive locations command failed: FileName={0} Arguments={1} ExitCode={2}</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="6263f-116">説明</span><span class="sxs-lookup"><span data-stu-id="6263f-116">Explanation</span></span>  
 <span data-ttu-id="6263f-117">発行ウィザードは、受信場所を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6263f-117">The publishing wizard failed to create a receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6263f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6263f-118">User Action</span></span>  
 <span data-ttu-id="6263f-119">このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6263f-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="6263f-120">作成の詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="6263f-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6263f-121">分離 WCF 受信アダプターでの WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="6263f-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="6263f-122">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6263f-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="6263f-123">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6263f-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="6263f-124">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6263f-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="6263f-125">チュートリアル: Wcf-basichttp アダプターで WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="6263f-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)