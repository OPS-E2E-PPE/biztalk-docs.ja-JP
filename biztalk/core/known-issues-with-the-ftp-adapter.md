---
title: FTP アダプターに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e58f2db-9ec5-41fe-af02-9a7d60a217db
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13ce12e8514eaa2b5843ba81eff4f505e65d9e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010091"
---
# <a name="known-issues-with-the-ftp-adapter"></a><span data-ttu-id="70a63-102">FTP アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="70a63-102">Known Issues with the FTP Adapter</span></span>
<span data-ttu-id="70a63-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="70a63-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="70a63-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="70a63-104">Known Issues</span></span>  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a><span data-ttu-id="70a63-105">BizTalk Server で FTP アダプターを使用してデータを受信すると、データが重複または損失する場合がある</span><span class="sxs-lookup"><span data-stu-id="70a63-105">Data may be duplicated or lost when you receive data in BizTalk Server by using the FTP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="70a63-106">問題</span><span class="sxs-lookup"><span data-stu-id="70a63-106">Problem</span></span>  
 <span data-ttu-id="70a63-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で FTP アダプターを使用してデータを受信すると、データの重複または損失が発生します。</span><span class="sxs-lookup"><span data-stu-id="70a63-107">Data is duplicated or lost when you receive data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the FTP Adapter.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="70a63-108">原因</span><span class="sxs-lookup"><span data-stu-id="70a63-108">Cause</span></span>  
 <span data-ttu-id="70a63-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプターは、指定された FTP サーバーを FTP クライアント プロトコルを使用してポーリングし、サーバーからデータを "そのまま" の状態で取得します。</span><span class="sxs-lookup"><span data-stu-id="70a63-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter uses the FTP client protocol to poll the designated FTP server and retrieves data from the server "as is."</span></span> <span data-ttu-id="70a63-110">FTP アダプターは、取得するデータを検証しません。</span><span class="sxs-lookup"><span data-stu-id="70a63-110">The FTP adapter does not validate any data that it retrieves.</span></span> <span data-ttu-id="70a63-111">FTP アダプターは、取得したドキュメントを処理のため BizTalk メッセージング エンジンに送信した後、FTP サーバーから元のドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="70a63-111">The FTP adapter sends the retrieved document to the BizTalk Messaging Engine for processing and then it deletes the original document from the FTP server.</span></span> <span data-ttu-id="70a63-112">FTP アダプターが、ホスト アプリケーションが書き込み中のドキュメントを FTP サーバーから取得すると、取得したドキュメントは不完全になります。</span><span class="sxs-lookup"><span data-stu-id="70a63-112">If the FTP adapter retrieves a document from the FTP server that is still being written to by the host application, the retrieved document will be incomplete.</span></span> <span data-ttu-id="70a63-113">元のドキュメントの不完全なコピーを取得した場合、次のシナリオでデータの重複やデータの損失が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="70a63-113">If the FTP adapter retrieves an incomplete copy of the original document, data duplication or data loss may occur in the following scenarios:</span></span>  
  
-   <span data-ttu-id="70a63-114">元のドキュメントがホスト アプリケーションから FTP サーバーに書き込まれている最中の場合、FTP アダプターはそのドキュメントを削除できないので、受信場所に構成された次のポーリング間隔でそのドキュメントのコピーをもう 1 つ取得します。</span><span class="sxs-lookup"><span data-stu-id="70a63-114">If the original document is still being written to the FTP server by the host application, the FTP adapter cannot delete the document and will retrieve another copy of the document at the next polling interval that is configured for the receive location.</span></span> <span data-ttu-id="70a63-115">この動作により、ドキュメントの重複が発生します。</span><span class="sxs-lookup"><span data-stu-id="70a63-115">This behavior causes document duplication to occur.</span></span>  
  
-   <span data-ttu-id="70a63-116">ホスト アプリケーションから FTP サーバーへのドキュメントの書き込みが完了すると、そのドキュメントは削除されます。</span><span class="sxs-lookup"><span data-stu-id="70a63-116">If the host application has finished writing the document to the FTP server, the document will be deleted.</span></span> <span data-ttu-id="70a63-117">この動作により、データの損失が発生します。</span><span class="sxs-lookup"><span data-stu-id="70a63-117">This behavior will cause data loss to occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="70a63-118">解決策</span><span class="sxs-lookup"><span data-stu-id="70a63-118">Resolution</span></span>  
 <span data-ttu-id="70a63-119">この動作を回避するには、以下のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="70a63-119">To work around this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="70a63-120">パブリック FTP フォルダーと同じハード ディスク上の一時フォルダーに書き込み、一時フォルダーの内容を定期的に FTP フォルダーに移動するように、ホスト アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="70a63-120">Configure the host application to write to a temporary folder on the same hard disk as the public FTP folder and to periodically move the contents of the temporary folder to the FTP folder.</span></span> <span data-ttu-id="70a63-121">移動操作がアトミックになるように、一時フォルダーを、パブリック FTP フォルダーと同じハード ディスク上に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70a63-121">The temporary folder should be on the same hard disk as the public FTP folder to make sure that the move operation is atomic.</span></span> <span data-ttu-id="70a63-122">アトミック操作とは、機能的にそれ以上分割できない操作のことです。</span><span class="sxs-lookup"><span data-stu-id="70a63-122">An atomic operation is an operation that is functionally indivisible.</span></span> <span data-ttu-id="70a63-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプターを使用してデータをパブリック FTP フォルダーに書き込む場合、この操作を行うには、送信ポートの構成時に [FTP トランスポートのプロパティ] ダイアログ ボックスで "一時フォルダー" プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="70a63-123">If you write data to the public FTP folder by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter, you can do this by specifying a Temporary Folder property in the FTP Transport Properties dialog box when you configure a send port.</span></span> <span data-ttu-id="70a63-124">"一時フォルダー" プロパティを指定する場合は、このフォルダーがパブリック FTP フォルダーと同じ物理ディスク上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70a63-124">If you specify a Temporary Folder property, make sure that this folder is on the same physical disk as the public FTP folder.</span></span>  
  
-   <span data-ttu-id="70a63-125">ホスト アプリケーションがデータを FTP サーバーに書き込まない場合、サービス時間帯に動作するように FTP 受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="70a63-125">Configure the FTP receive location to operate within a service window when the host application is not writing data to the FTP server.</span></span> <span data-ttu-id="70a63-126">サービス時間帯は、受信場所のプロパティを構成する際に指定できます。</span><span class="sxs-lookup"><span data-stu-id="70a63-126">You can specify the service window when you configure the receive location properties.</span></span>  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a><span data-ttu-id="70a63-127">FTP アダプターではサーバー証明書の失効の確認をサポートしていない</span><span class="sxs-lookup"><span data-stu-id="70a63-127">FTP Adapter does not support revocation checks on the server certificates</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="70a63-128">問題</span><span class="sxs-lookup"><span data-stu-id="70a63-128">Problem</span></span>  
 <span data-ttu-id="70a63-129">BizTalk Server で FTP アダプターは、SSL/TLS を使用した FTPS サーバーとの間のセキュリティで保護されたファイル転送をサポートするために強化されました。</span><span class="sxs-lookup"><span data-stu-id="70a63-129">The FTP adapter in BizTalk Server is enhanced to support secure file transfer to and from an FTPS server using SSL/TLS.</span></span> <span data-ttu-id="70a63-130">証明書失効リスト (CRL) には失効し、無効になった証明書のリストが入っています。</span><span class="sxs-lookup"><span data-stu-id="70a63-130">The Certificate Revocation List (CRL) contains a list of certificates that have been revoked and are no longer valid.</span></span> <span data-ttu-id="70a63-131">FTP アダプターでは、サーバー証明書を認証するために CRL を参照しません。</span><span class="sxs-lookup"><span data-stu-id="70a63-131">The FTP adapter does not consult the CRL for authenticating the server certificate.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="70a63-132">原因</span><span class="sxs-lookup"><span data-stu-id="70a63-132">Cause</span></span>  
 <span data-ttu-id="70a63-133">仕様上、FTP アダプターではサーバー証明書を受け取る前に CRL を参照しません。</span><span class="sxs-lookup"><span data-stu-id="70a63-133">By design, the FTP adapter does not consult the CRL before accepting a server certificate.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="70a63-134">解決策</span><span class="sxs-lookup"><span data-stu-id="70a63-134">Resolution</span></span>  
 <span data-ttu-id="70a63-135">操作は不要です。この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="70a63-135">No action is required; this behavior is by design.</span></span>  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a><span data-ttu-id="70a63-136">FTP アダプターで最大ファイル サイズを超えるファイルがダウンロードされる</span><span class="sxs-lookup"><span data-stu-id="70a63-136">FTP Adapter downloads files larger than Max File Size</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="70a63-137">問題</span><span class="sxs-lookup"><span data-stu-id="70a63-137">Problem</span></span>  
 <span data-ttu-id="70a63-138">FTP 受信アダプターでは、指定した最大ファイル サイズ プロパティを超えるサイズのファイルが次の FTP サーバーからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="70a63-138">The FTP receive adapter downloads files whose size is larger than the specified Max File Size property from the following FTP servers:</span></span>  
  
-   <span data-ttu-id="70a63-139">AIX</span><span class="sxs-lookup"><span data-stu-id="70a63-139">AIX</span></span>  
  
-   <span data-ttu-id="70a63-140">MVS</span><span class="sxs-lookup"><span data-stu-id="70a63-140">MVS</span></span>  
  
-   <span data-ttu-id="70a63-141">AS400</span><span class="sxs-lookup"><span data-stu-id="70a63-141">AS400</span></span>  
  
-   <span data-ttu-id="70a63-142">GXS</span><span class="sxs-lookup"><span data-stu-id="70a63-142">GXS</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="70a63-143">原因</span><span class="sxs-lookup"><span data-stu-id="70a63-143">Cause</span></span>  
 <span data-ttu-id="70a63-144">仕様上、FTP アダプターでは上記の FTP サーバーからファイルをダウンロードするとき、最大ファイル サイズの設定に従いません。</span><span class="sxs-lookup"><span data-stu-id="70a63-144">By design, the FTP adapter does not respect the maximum file size when downloading files from these FTP servers.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="70a63-145">解決策</span><span class="sxs-lookup"><span data-stu-id="70a63-145">Resolution</span></span>  
 <span data-ttu-id="70a63-146">操作は不要です。この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="70a63-146">No action is required; this behavior is by design.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a63-147">参照</span><span class="sxs-lookup"><span data-stu-id="70a63-147">See Also</span></span>  
 <span data-ttu-id="70a63-148">[FTP 受信場所を構成する方法](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span><span class="sxs-lookup"><span data-stu-id="70a63-148">[How to Configure an FTP Receive Location](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span></span>  
 [<span data-ttu-id="70a63-149">FTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="70a63-149">Troubleshooting the FTP Adapter</span></span>](../core/troubleshooting-the-ftp-adapter.md)