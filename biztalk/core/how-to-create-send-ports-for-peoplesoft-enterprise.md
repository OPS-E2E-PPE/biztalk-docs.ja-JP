---
title: "PeopleSoft Enterprise の送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 374261ce-2cb5-4193-a0a2-658f989b2c60
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b6b5caa44976aec7a4afb8e0eccf5b1f8904111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="5c21b-102">PeopleSoft Enterprise の送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="5c21b-102">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="5c21b-103">BizTalk Server 管理コンソールを使用して送信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c21b-103">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="5c21b-104">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="5c21b-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="5c21b-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="5c21b-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="5c21b-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="5c21b-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="5c21b-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="5c21b-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="5c21b-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5c21b-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="5c21b-109">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。</span><span class="sxs-lookup"><span data-stu-id="5c21b-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="5c21b-110">**型**ドロップダウン リストで、 **PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="5c21b-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="5c21b-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c21b-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="5c21b-112">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="5c21b-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="5c21b-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="5c21b-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="5c21b-114">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c21b-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="5c21b-115">**PeopleSoft トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5c21b-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="5c21b-116">展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5c21b-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="5c21b-117">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c21b-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="5c21b-118">一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c21b-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="5c21b-119">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="5c21b-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="5c21b-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c21b-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="5c21b-121">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c21b-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c21b-122">参照</span><span class="sxs-lookup"><span data-stu-id="5c21b-122">See Also</span></span>  
 [<span data-ttu-id="5c21b-123">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="5c21b-123">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)