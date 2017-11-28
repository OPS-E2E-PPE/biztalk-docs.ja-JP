---
title: "Mdn の HTTP 設定の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c877e85-7887-43a9-9fd4-0853b573213f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74ba2eaf11e8beed3e28d10beb9f95b2f0f6194
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-http-settings-for-mdns"></a><span data-ttu-id="b9240-102">MDN の HTTP 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b9240-102">Configuring HTTP Settings for MDNs</span></span>
<span data-ttu-id="b9240-103">MDN 関連の HTTP 設定の一部として、MDN を受信する Web サーバーが予期するプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b9240-103">As part of MDN-related HTTP settings, you can specify the properties expected by the Web server that receives the MDNs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9240-104">オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="b9240-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="b9240-105">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="b9240-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="b9240-106">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="b9240-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9240-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="b9240-107">Prerequisites</span></span>  
 <span data-ttu-id="b9240-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9240-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-mdn-related-http-settings"></a><span data-ttu-id="b9240-109">MDN 関連の HTTP 設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="b9240-109">To configure MDN-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="b9240-110">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="b9240-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="b9240-111">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="b9240-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b9240-112">一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、 **Mdn の HTTP 設定**です。</span><span class="sxs-lookup"><span data-stu-id="b9240-112">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for MDNs**.</span></span>  
  
3.  <span data-ttu-id="b9240-113">選択、**を無視する SSL 証明書名の不一致**サーバー名が SSL 証明書の生成対象サーバー名が一致しない場合、SSL 接続があることを確認する チェック ボックスが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="b9240-113">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="b9240-114">をクリックして**HTTP expect 100 continue** HTTP Expect ヘッダーを 100 に設定する-続行すると、ポストされたデータを最初の HTTP 要求が、サーバー コンテンツを要求するまで待機に含まれないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9240-114">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="b9240-115">をクリックして**保持の HTTP 接続をアライブ**こと、HTTP 接続維持される要求と応答のサイクルが完了した後に要求します。</span><span class="sxs-lookup"><span data-stu-id="b9240-115">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="b9240-116">をクリックして**を展開する HTTP ヘッダー** HTTP content-type ヘッダーを 1 行に展開する場合。</span><span class="sxs-lookup"><span data-stu-id="b9240-116">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="b9240-117">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b9240-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9240-118">参照</span><span class="sxs-lookup"><span data-stu-id="b9240-118">See Also</span></span>  
 [<span data-ttu-id="b9240-119">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="b9240-119">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)