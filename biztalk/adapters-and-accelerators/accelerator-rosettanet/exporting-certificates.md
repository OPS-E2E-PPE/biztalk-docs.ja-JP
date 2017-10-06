---
title: "証明書のエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1898162b27956e4e527013ff765edf6aea440e9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-certificates"></a><span data-ttu-id="2c57f-102">証明書のエクスポート</span><span class="sxs-lookup"><span data-stu-id="2c57f-102">Exporting Certificates</span></span>
<span data-ttu-id="2c57f-103">ここでは、証明書のエクスポート ウィザードを使用して証明書をエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c57f-103">This topic describes how to export a certificate by using the Certificate Export Wizard.</span></span> <span data-ttu-id="2c57f-104">このウィザードを使用すると、パブリック証明書またはプライベート証明書のいずれかをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="2c57f-104">Use this wizard to export either a public certificate or a private certificate.</span></span>  
  
### <a name="to-export-a-partner-certificate"></a><span data-ttu-id="2c57f-105">パートナー証明書をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="2c57f-105">To export a partner certificate</span></span>  
  
1.  <span data-ttu-id="2c57f-106">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] をクリックし、 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="2c57f-106">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="2c57f-107">展開**証明書 (ローカル コンピューター)**、展開**ほかの人**、クリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-107">Expand **Certificates (Local Computer)**, expand **Other People**, and then click **Certificates**.</span></span>  
  
3.  <span data-ttu-id="2c57f-108">右側のウィンドウで、証明書の名前を右クリックし、**すべてのタスク**、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-108">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4.  <span data-ttu-id="2c57f-109">**証明書のエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-109">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2c57f-110">**エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c57f-110">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="2c57f-111">この形式は、通常、バイナリ エンコード ファイルをエクスポートする DER encoded binary x.509 か、Base-64 エンコード ファイルをエクスポートする Base-64 encoded x.509 のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="2c57f-111">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c57f-112">Base-64 で証明書をエンコードすると、その証明書を UNIX サーバーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c57f-112">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
6.  <span data-ttu-id="2c57f-113">**エクスポートするファイル** ページで、をクリックして**参照**、検索、ファイルの名前を入力ファイルを保存する場所をクリックして**次へ**、順にクリック**完了**.</span><span class="sxs-lookup"><span data-stu-id="2c57f-113">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-export-the-home-organization-certificate"></a><span data-ttu-id="2c57f-114">ホーム組織証明書をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="2c57f-114">To export the home organization certificate</span></span>  
  
1.  <span data-ttu-id="2c57f-115">をクリックして**開始**をクリックして**実行**、型**runas/user:\<サービスをホスト > mmc**ここで、 \< *hostservice*> をインストールしたときに、ホスト サービスに関連付けられたサービスの名前を指定[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、順にクリック**OK**を実行する、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]のコンテキストで管理コンソール (MMC)、ホスト サービス。</span><span class="sxs-lookup"><span data-stu-id="2c57f-115">Click **Start**, click **Run**, type **runas /user:\<host service> mmc**, where \<*hostservice*> is the name of the service that you associated with the host service when you installed [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], and then click **OK** to run the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC) in the context of the host service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c57f-116">実行する、 **runas**コマンドをホーム組織証明書にアクセスに必要なホスト サービスの id を前提としています。</span><span class="sxs-lookup"><span data-stu-id="2c57f-116">You run the **runas** command to assume the identity of the host service, which is required to access the home-organization certificate.</span></span>  
  
2.  <span data-ttu-id="2c57f-117">展開**証明書 - 現在のユーザー**、展開**個人**、クリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-117">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
3.  <span data-ttu-id="2c57f-118">右側のウィンドウで、証明書の名前を右クリックし、**すべてのタスク**、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-118">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4.  <span data-ttu-id="2c57f-119">**証明書のエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-119">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2c57f-120">証明書の秘密キーに関連付けられている公開キーをエクスポートするのままにして**いいえ、秘密キーをエクスポートしません**選択します。</span><span class="sxs-lookup"><span data-stu-id="2c57f-120">To export the public key associated with the private key of a certificate, leave **No, do not export the private key** selected.</span></span> <span data-ttu-id="2c57f-121">秘密キーをエクスポートするには選択**はい、秘密キーをエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="2c57f-121">To export the private key, select **Yes, export the private key**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c57f-122">選択した場合**はい、秘密キーをエクスポート**パートナーに、生成されたファイルを送信しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c57f-122">If you select **Yes, export the private key**, it is highly recommended that you do not send the resulting file to a partner.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c57f-123">**はい、秘密キーをエクスポート**されませんを行った場合、秘密キー エクスポート可能な最初にインポートしたときにオプションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2c57f-123">The **Yes, export the private key** option will not be available if you did not make the private key exportable when you first imported it.</span></span>  
  
6.  <span data-ttu-id="2c57f-124">**エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c57f-124">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="2c57f-125">この形式は、通常、バイナリ エンコード ファイルをエクスポートする DER encoded binary x.509 か、Base-64 エンコード ファイルをエクスポートする Base-64 encoded x.509 のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="2c57f-125">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c57f-126">Base-64 で証明書をエンコードすると、その証明書を UNIX サーバーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c57f-126">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
7.  <span data-ttu-id="2c57f-127">**エクスポートするファイル** ページで、をクリックして**参照**、検索、ファイルの名前を入力ファイルを保存する場所をクリックして**次へ**、順にクリック**完了**.</span><span class="sxs-lookup"><span data-stu-id="2c57f-127">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c57f-128">参照</span><span class="sxs-lookup"><span data-stu-id="2c57f-128">See Also</span></span>  
 [<span data-ttu-id="2c57f-129">証明書の管理</span><span class="sxs-lookup"><span data-stu-id="2c57f-129">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)