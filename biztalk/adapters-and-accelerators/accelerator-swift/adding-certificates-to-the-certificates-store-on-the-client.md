---
title: クライアントの証明書ストアに証明書の追加 |Microsoft Docs
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
ms.assetid: 9e2722ee-dd6f-4b14-9796-2f2157e8cad2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56a953ceaddd02df5e258ceb3034a29f6e56aff7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378902"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-client"></a><span data-ttu-id="1e500-102">クライアントの証明書ストアに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="1e500-102">Adding Certificates to the Certificates Store on the Client</span></span>
<span data-ttu-id="1e500-103">次の手順を使用すると、各クライアント コンピューター上の証明書ストアの個人用フォルダーに証明書を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1e500-103">Use the following steps to add certificates to the Personal folder in the certificates store on each client computer.</span></span> <span data-ttu-id="1e500-104">証明書 - 現在のユーザー ストアの個人用フォルダーに、証明書を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e500-104">The certificates must be added to the Personal folder in the Certificates - Current User store.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e500-105">証明書を使用して配布されていない場合は、エンタープライズ証明機関を信頼された、クライアント コンピューターに証明機関のルート証明書をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e500-105">If your certificates are not distributed via an enterprise trusted Certification Authority, you must import the Certification Authority's root certificate onto the client computer(s).</span></span> <span data-ttu-id="1e500-106">それ以外の場合、個人証明書は機能しません。</span><span class="sxs-lookup"><span data-stu-id="1e500-106">Otherwise, your personal certificates will not work.</span></span> <span data-ttu-id="1e500-107">証明書 (ローカル コンピュータ) ノードでの信頼されたルート証明機関フォルダーには、証明機関の証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="1e500-107">Import the Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) node.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="1e500-108">証明書ストアに証明書を追加するには</span><span class="sxs-lookup"><span data-stu-id="1e500-108">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="1e500-109">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e500-109">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="1e500-110">入力**mmc**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="1e500-110">Enter **mmc**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="1e500-111">Console1 ダイアログ ボックスで、**ファイル**、 をクリックし、**スナップインの追加と削除**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-111">In the Console1 dialog box, click **File**, and then click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="1e500-112">[スナップインの追加と削除] ダイアログ ボックスで、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-112">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="1e500-113">スタンドアロン スナップインの追加 ダイアログ ボックスで、**証明書**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-113">In the Add Standalone Snap-in dialog box, click **Certificates**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="1e500-114">証明書スナップイン ダイアログ ボックスで、次のようにクリックします。 **ユーザー アカウント**、 をクリックし、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-114">In the Certificates snap-in dialog box, click **My user account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="1e500-115">スタンドアロン スナップインの追加 ダイアログ ボックスで、**証明書**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-115">In the Add Standalone Snap-in dialog box, click **Certificates**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="1e500-116">証明書スナップイン ダイアログ ボックスで、次のようにクリックします。**コンピューター アカウント**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="1e500-116">In the Certificates snap-in dialog box, click **Computer account**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="1e500-117">コンピューターの選択 ダイアログ ボックスで確認**ローカル コンピューター**が選択されているし、をクリックし、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-117">In the Select Computer dialog box, make sure **Local computer** is selected, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="1e500-118">[スタンドアロン スナップインの追加] ダイアログ ボックスで、**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-118">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="1e500-119">[スナップインの追加と削除] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-119">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="1e500-120">**コンソール ルート**Console1 ダイアログ ボックスのペインの展開、**証明書 - 現在のユーザー**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="1e500-120">In the **Console Root** pane of the Console1 dialog box, expand the **Certificates - Current User** folders.</span></span>  
  
12. <span data-ttu-id="1e500-121">**証明書 - 現在のユーザー**、展開**個人**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-121">Under **Certificates - Current User**, expand **Personal**.</span></span>  
  
13. <span data-ttu-id="1e500-122">右クリック**証明書**、 をポイント**すべてのタスク**、 をクリックし、**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-122">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
14. <span data-ttu-id="1e500-123">証明書のインポート ウィザードのページへようこそ、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-123">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
15. <span data-ttu-id="1e500-124">ファイルのインポート ページで、をクリックして**参照**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-124">On the File to Import page, click **Browse**.</span></span>  
  
16. <span data-ttu-id="1e500-125">[開く] ダイアログ ボックスで、証明書の選択を保存したファイルの場所に移動します**すべてのファイル**の**ファイルの種類**、クリックして、インポートする証明書を選択 **。開いている**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-125">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
17. <span data-ttu-id="1e500-126">ファイルのインポート ページで、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-126">On the File to Import page, click **Next**.</span></span>  
  
18. <span data-ttu-id="1e500-127">証明書ストア] ページで、ことを確認します**次のストアに証明書をすべてを配置**が選択されていることを確認します**個人**に表示される、**証明書ストア**クリックして、ボックスの [**次**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-127">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Personal** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
19. <span data-ttu-id="1e500-128">完了証明書のインポート ウィザード ページで、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-128">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
20. <span data-ttu-id="1e500-129">[インポートに成功を示す証明書のインポート ウィザード] ダイアログ ボックス、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="1e500-129">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
21. <span data-ttu-id="1e500-130">手順 13 ~ 20 は、メッセージの修復と新しい送信で使用するその他のすべての証明書を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1e500-130">Repeat steps 13 through 20 for all other certificates that you will use in message repair and new submission.</span></span>