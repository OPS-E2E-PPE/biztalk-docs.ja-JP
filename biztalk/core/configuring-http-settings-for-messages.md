---
title: メッセージの HTTP 設定の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed400f1-561d-4812-adf1-20e4300fd048
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d15ebb5ff5be6678c4dc2aee3f9333f36c75c89f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233090"
---
# <a name="configuring-http-settings-for-messages"></a><span data-ttu-id="f1d3e-102">メッセージの HTTP 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-102">Configuring HTTP Settings for Messages</span></span>
<span data-ttu-id="f1d3e-103">メッセージ関連の HTTP 設定の一部として、AS2 メッセージを受信する Web サーバーが予期するプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-103">As part of message-related HTTP settings, you can specify the properties expected by the Web server that receives AS2 messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1d3e-104">プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合</span><span class="sxs-lookup"><span data-stu-id="f1d3e-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f1d3e-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="f1d3e-105">Prerequisites</span></span>  
 <span data-ttu-id="f1d3e-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-related-http-settings"></a><span data-ttu-id="f1d3e-107">メッセージ関連の HTTP 設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="f1d3e-107">To configure message-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="f1d3e-108">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="f1d3e-109">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f1d3e-110">一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、**メッセージの HTTP 設定**です。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-110">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for Messages**.</span></span>  
  
3.  <span data-ttu-id="f1d3e-111">選択、**を無視する SSL 証明書名の不一致**サーバー名が SSL 証明書の生成対象サーバー名が一致しない場合、SSL 接続があることを確認する チェック ボックスが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-111">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="f1d3e-112">をクリックして**HTTP expect 100 continue** HTTP Expect ヘッダーを 100 に設定する-続行すると、ポストされたデータを最初の HTTP 要求が、サーバー コンテンツを要求するまで待機に含まれないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-112">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="f1d3e-113">をクリックして**保持の HTTP 接続をアライブ**こと、HTTP 接続維持される要求と応答のサイクルが完了した後に要求します。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-113">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="f1d3e-114">をクリックして**を展開する HTTP ヘッダー** HTTP content-type ヘッダーを 1 行に展開する場合。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-114">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="f1d3e-115">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f1d3e-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d3e-116">参照</span><span class="sxs-lookup"><span data-stu-id="f1d3e-116">See Also</span></span>  
 [<span data-ttu-id="f1d3e-117">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="f1d3e-117">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)