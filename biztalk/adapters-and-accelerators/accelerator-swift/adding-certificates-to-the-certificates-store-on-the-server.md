---
title: サーバー上の証明書ストアに証明書を追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94661568108e5a1cc05140a97c933fb8d00e3c67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209570"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a><span data-ttu-id="b17c5-102">サーバー上の証明書ストアに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="b17c5-102">Adding Certificates to the Certificates Store on the Server</span></span>
<span data-ttu-id="b17c5-103">サーバー コンピューター上の証明書 (ローカル コンピューター) ストアにその他のユーザー フォルダーに証明書を追加するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b17c5-103">Use the following steps to add certificates to the Other People folder in the Certificates (Local Computer) store on the server computer.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="b17c5-104">証明書ストアに証明書を追加するには</span><span class="sxs-lookup"><span data-stu-id="b17c5-104">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="b17c5-105">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator 用 SWIFT**、順にクリック**BizTalk Accelerator for SWIFT の管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BizTalk Accelerator for SWIFT Management Console**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b17c5-106">前の手順 (追加する証明書クライアントで証明書ストアを) 開く MMC ウィンドウをまだある場合は場合、は、この手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b17c5-106">If you still have the MMC window open from the previous procedure (Adding Certificates to the Certificates Store on the Client), you can use it for this procedure.</span></span>  
  
2.  <span data-ttu-id="b17c5-107">管理コンソール ウィンドウで、**証明書 (ローカル コンピューター)** フォルダーの順に展開および**ほかの人**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-107">In the Administration Console window, expand the **Certificates (Local Computer)** folder, and then expand **Other People**.</span></span>  
  
3.  <span data-ttu-id="b17c5-108">右クリック**証明書**、 をポイント**すべてのタスク**、クリックして**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-108">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
4.  <span data-ttu-id="b17c5-109">証明書のインポート ウィザードのページへようこそ、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-109">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="b17c5-110">ファイルのインポート ページで、をクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-110">On the File to Import page, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="b17c5-111">[開く] ダイアログ ボックスで、証明書の選択を保存したファイルの場所に移動**すべてのファイル**の**ファイルの種類**、クリックして、インポートする証明書を選択**開いている**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-111">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="b17c5-112">ファイルのインポート ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-112">On the File to Import page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b17c5-113">証明書ストア ページで、いることを確認**次のストアに証明書をすべてを配置**が選択されていることを確認**ほかの人**に表示される、**証明書ストア**ボックスをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-113">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Other People** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="b17c5-114">完了証明書のインポート ウィザードのページでをクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-114">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
10. <span data-ttu-id="b17c5-115">[正常なインポートを示す証明書のインポート ウィザード] ダイアログ ボックス、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="b17c5-115">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
11. <span data-ttu-id="b17c5-116">メッセージの修復と新しい送信で使用するその他のすべての証明書には、手順 3. ~ 10. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b17c5-116">Repeat steps 3 through 10 for all other certificates that you will use in message repair and new submission.</span></span>