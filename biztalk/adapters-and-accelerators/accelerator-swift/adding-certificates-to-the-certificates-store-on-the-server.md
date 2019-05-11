---
title: サーバーの証明書ストアに証明書の追加 |Microsoft Docs
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
ms.openlocfilehash: 973dc2caa5fd3950a8e1bebb74cf2c3e13806d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378880"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a><span data-ttu-id="63a8a-102">サーバーの証明書ストアに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-102">Adding Certificates to the Certificates Store on the Server</span></span>
<span data-ttu-id="63a8a-103">次の手順を使用すると、サーバー コンピューター (ローカル コンピューター) の証明書ストア内の他のユーザー フォルダーに証明書を追加できます。</span><span class="sxs-lookup"><span data-stu-id="63a8a-103">Use the following steps to add certificates to the Other People folder in the Certificates (Local Computer) store on the server computer.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="63a8a-104">証明書ストアに証明書を追加するには</span><span class="sxs-lookup"><span data-stu-id="63a8a-104">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="63a8a-105">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BizTalk Accelerator for SWIFT の管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BizTalk Accelerator for SWIFT Management Console**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="63a8a-106">前の手順 (追加の証明書クライアントで証明書ストアに) から開く MMC ウィンドウをまだ場合は、この手順で使用できます。</span><span class="sxs-lookup"><span data-stu-id="63a8a-106">If you still have the MMC window open from the previous procedure (Adding Certificates to the Certificates Store on the Client), you can use it for this procedure.</span></span>  
  
2.  <span data-ttu-id="63a8a-107">管理コンソール ウィンドウで、**証明書 (ローカル コンピューター)** フォルダーを順に展開**その他のユーザー**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-107">In the Administration Console window, expand the **Certificates (Local Computer)** folder, and then expand **Other People**.</span></span>  
  
3.  <span data-ttu-id="63a8a-108">右クリック**証明書**、 をポイント**すべてのタスク**、 をクリックし、**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-108">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
4.  <span data-ttu-id="63a8a-109">証明書のインポート ウィザードのページへようこそ、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-109">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="63a8a-110">ファイルのインポート ページで、をクリックして**参照**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-110">On the File to Import page, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="63a8a-111">[開く] ダイアログ ボックスで、証明書の選択を保存したファイルの場所に移動します**すべてのファイル**の**ファイルの種類**、クリックして、インポートする証明書を選択 **。開いている**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-111">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="63a8a-112">ファイルのインポート ページで、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-112">On the File to Import page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="63a8a-113">証明書ストア ページで、ことを確認します**次のストアに証明書をすべてを配置**が選択されていることを確認します**その他のユーザー**に表示される、**証明書ストア**ボックスをクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-113">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Other People** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="63a8a-114">完了証明書のインポート ウィザード ページで、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-114">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
10. <span data-ttu-id="63a8a-115">[インポートに成功を示す証明書のインポート ウィザード] ダイアログ ボックス、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-115">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
11. <span data-ttu-id="63a8a-116">手順 3 ~ 10 メッセージの修復と新しい送信で使用するその他のすべての証明書を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63a8a-116">Repeat steps 3 through 10 for all other certificates that you will use in message repair and new submission.</span></span>