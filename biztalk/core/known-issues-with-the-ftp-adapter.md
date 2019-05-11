---
title: FTP アダプターに関する既知の問題 |Microsoft Docs
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
ms.openlocfilehash: 682e87e2cfca4906b0f9c582d5e33a235525e293
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329108"
---
# <a name="known-issues-with-the-ftp-adapter"></a><span data-ttu-id="c9dee-102">FTP アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="c9dee-102">Known Issues with the FTP Adapter</span></span>
<span data-ttu-id="c9dee-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="c9dee-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="c9dee-104">Known Issues</span></span>  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a><span data-ttu-id="c9dee-105">データを複製または BizTalk Server で FTP アダプターを使用してデータを受信するときに失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9dee-105">Data may be duplicated or lost when you receive data in BizTalk Server by using the FTP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c9dee-106">問題</span><span class="sxs-lookup"><span data-stu-id="c9dee-106">Problem</span></span>  
 <span data-ttu-id="c9dee-107">データの重複またはデータを受信するときに失われる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]FTP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-107">Data is duplicated or lost when you receive data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the FTP Adapter.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c9dee-108">原因</span><span class="sxs-lookup"><span data-stu-id="c9dee-108">Cause</span></span>  
 <span data-ttu-id="c9dee-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプター、FTP クライアント プロトコルを使用して、指定された FTP サーバーをポーリングおよび"です。」と、サーバーからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter uses the FTP client protocol to poll the designated FTP server and retrieves data from the server "as is."</span></span> <span data-ttu-id="c9dee-110">FTP アダプターでは、取得したデータは検証されません。</span><span class="sxs-lookup"><span data-stu-id="c9dee-110">The FTP adapter does not validate any data that it retrieves.</span></span> <span data-ttu-id="c9dee-111">FTP アダプターが、BizTalk メッセージング エンジンで処理するために取得したドキュメントを送信し、元のドキュメント、FTP サーバーから削除します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-111">The FTP adapter sends the retrieved document to the BizTalk Messaging Engine for processing and then it deletes the original document from the FTP server.</span></span> <span data-ttu-id="c9dee-112">FTP アダプターは、ホスト アプリケーションによってにまだ書き込まれている FTP サーバーからドキュメントを取得する場合、取得したドキュメントは完了できません。</span><span class="sxs-lookup"><span data-stu-id="c9dee-112">If the FTP adapter retrieves a document from the FTP server that is still being written to by the host application, the retrieved document will be incomplete.</span></span> <span data-ttu-id="c9dee-113">FTP アダプターは、元のドキュメントの不完全なコピーを取得する場合、次のシナリオでデータの重複やデータの損失は発生します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-113">If the FTP adapter retrieves an incomplete copy of the original document, data duplication or data loss may occur in the following scenarios:</span></span>  
  
-   <span data-ttu-id="c9dee-114">場合は、元のドキュメントは、ホスト アプリケーションによって FTP サーバーにまだ書き込まれるは、FTP アダプター、ドキュメントを削除することはできず、次のポーリング間隔で構成されている受信場所のドキュメントの別のコピーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-114">If the original document is still being written to the FTP server by the host application, the FTP adapter cannot delete the document and will retrieve another copy of the document at the next polling interval that is configured for the receive location.</span></span> <span data-ttu-id="c9dee-115">この動作により、ドキュメントの重複が発生します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-115">This behavior causes document duplication to occur.</span></span>  
  
-   <span data-ttu-id="c9dee-116">ホスト アプリケーションが FTP サーバーへのドキュメントの書き込みを終了すると、ドキュメントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9dee-116">If the host application has finished writing the document to the FTP server, the document will be deleted.</span></span> <span data-ttu-id="c9dee-117">この動作には、発生するデータの損失が発生します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-117">This behavior will cause data loss to occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c9dee-118">解決策</span><span class="sxs-lookup"><span data-stu-id="c9dee-118">Resolution</span></span>  
 <span data-ttu-id="c9dee-119">この問題を回避するには、次のメソッドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-119">To work around this behavior, use one of the following methods:</span></span>  
  
- <span data-ttu-id="c9dee-120">パブリック FTP フォルダーと同じハード_ディスク上の一時フォルダーに書き込むと、定期的に一時フォルダーの内容を FTP フォルダーに移動するホスト アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-120">Configure the host application to write to a temporary folder on the same hard disk as the public FTP folder and to periodically move the contents of the temporary folder to the FTP folder.</span></span> <span data-ttu-id="c9dee-121">一時フォルダーは、移動操作がアトミックであることを確認するパブリック FTP フォルダーと同じハード_ディスクになければなりません。</span><span class="sxs-lookup"><span data-stu-id="c9dee-121">The temporary folder should be on the same hard disk as the public FTP folder to make sure that the move operation is atomic.</span></span> <span data-ttu-id="c9dee-122">分割不可能な操作は、機能的割り切れない操作です。</span><span class="sxs-lookup"><span data-stu-id="c9dee-122">An atomic operation is an operation that is functionally indivisible.</span></span> <span data-ttu-id="c9dee-123">使用して、パブリック FTP フォルダーにデータを記述するかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプターでは、これを行う送信ポートを構成するときに、FTP トランスポートのプロパティ ダイアログ ボックスの一時フォルダのプロパティを指定しています。</span><span class="sxs-lookup"><span data-stu-id="c9dee-123">If you write data to the public FTP folder by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter, you can do this by specifying a Temporary Folder property in the FTP Transport Properties dialog box when you configure a send port.</span></span> <span data-ttu-id="c9dee-124">一時フォルダーのプロパティを指定する場合は、このフォルダーがパブリック FTP フォルダーと同じ物理ディスクにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c9dee-124">If you specify a Temporary Folder property, make sure that this folder is on the same physical disk as the public FTP folder.</span></span>  
  
- <span data-ttu-id="c9dee-125">構成、FTP 受信場所でホスト アプリケーションが FTP サーバーへのデータを書き込んでいないときに、サービス時間帯内で動作します。</span><span class="sxs-lookup"><span data-stu-id="c9dee-125">Configure the FTP receive location to operate within a service window when the host application is not writing data to the FTP server.</span></span> <span data-ttu-id="c9dee-126">受信場所のプロパティを構成するときに、サービス時間帯を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9dee-126">You can specify the service window when you configure the receive location properties.</span></span>  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a><span data-ttu-id="c9dee-127">FTP アダプターがサーバー証明書の失効の確認をサポートしていません</span><span class="sxs-lookup"><span data-stu-id="c9dee-127">FTP Adapter does not support revocation checks on the server certificates</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c9dee-128">問題</span><span class="sxs-lookup"><span data-stu-id="c9dee-128">Problem</span></span>  
 <span data-ttu-id="c9dee-129">BizTalk Server で FTP アダプターが拡張され、SSL や TLS を使用して、FTPS サーバーとの間にセキュリティで保護されたファイル転送をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c9dee-129">The FTP adapter in BizTalk Server is enhanced to support secure file transfer to and from an FTPS server using SSL/TLS.</span></span> <span data-ttu-id="c9dee-130">証明書失効リスト (CRL) には、失効し、無効になっている証明書の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9dee-130">The Certificate Revocation List (CRL) contains a list of certificates that have been revoked and are no longer valid.</span></span> <span data-ttu-id="c9dee-131">FTP アダプターでは、サーバー証明書を認証するため、CRL は参照しません。</span><span class="sxs-lookup"><span data-stu-id="c9dee-131">The FTP adapter does not consult the CRL for authenticating the server certificate.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c9dee-132">原因</span><span class="sxs-lookup"><span data-stu-id="c9dee-132">Cause</span></span>  
 <span data-ttu-id="c9dee-133">仕様上、FTP アダプターは、サーバー証明書を受け入れる前に CRL を参照しません。</span><span class="sxs-lookup"><span data-stu-id="c9dee-133">By design, the FTP adapter does not consult the CRL before accepting a server certificate.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c9dee-134">解決策</span><span class="sxs-lookup"><span data-stu-id="c9dee-134">Resolution</span></span>  
 <span data-ttu-id="c9dee-135">操作は不要です。この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="c9dee-135">No action is required; this behavior is by design.</span></span>  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a><span data-ttu-id="c9dee-136">FTP アダプターがファイルの最大サイズより大きいファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c9dee-136">FTP Adapter downloads files larger than Max File Size</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c9dee-137">問題</span><span class="sxs-lookup"><span data-stu-id="c9dee-137">Problem</span></span>  
 <span data-ttu-id="c9dee-138">FTP は、アダプターのダウンロード ファイルのサイズが次の FTP サーバーから指定した最大ファイル サイズ プロパティよりも大きいが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9dee-138">The FTP receive adapter downloads files whose size is larger than the specified Max File Size property from the following FTP servers:</span></span>  
  
-   <span data-ttu-id="c9dee-139">AIX</span><span class="sxs-lookup"><span data-stu-id="c9dee-139">AIX</span></span>  
  
-   <span data-ttu-id="c9dee-140">MVS</span><span class="sxs-lookup"><span data-stu-id="c9dee-140">MVS</span></span>  
  
-   <span data-ttu-id="c9dee-141">AS400</span><span class="sxs-lookup"><span data-stu-id="c9dee-141">AS400</span></span>  
  
-   <span data-ttu-id="c9dee-142">GXS</span><span class="sxs-lookup"><span data-stu-id="c9dee-142">GXS</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c9dee-143">原因</span><span class="sxs-lookup"><span data-stu-id="c9dee-143">Cause</span></span>  
 <span data-ttu-id="c9dee-144">仕様では、FTP アダプターはファイルの最大サイズを考慮しないこれらの FTP サーバーからファイルをダウンロードするときに。</span><span class="sxs-lookup"><span data-stu-id="c9dee-144">By design, the FTP adapter does not respect the maximum file size when downloading files from these FTP servers.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c9dee-145">解決策</span><span class="sxs-lookup"><span data-stu-id="c9dee-145">Resolution</span></span>  
 <span data-ttu-id="c9dee-146">操作は不要です。この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="c9dee-146">No action is required; this behavior is by design.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9dee-147">参照</span><span class="sxs-lookup"><span data-stu-id="c9dee-147">See Also</span></span>  
 <span data-ttu-id="c9dee-148">[FTP 受信場所を構成する方法](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span><span class="sxs-lookup"><span data-stu-id="c9dee-148">[How to Configure an FTP Receive Location](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span></span>  
 [<span data-ttu-id="c9dee-149">FTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c9dee-149">Troubleshooting the FTP Adapter</span></span>](../core/troubleshooting-the-ftp-adapter.md)