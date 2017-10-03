---
title: "SMTP アダプタのセキュリティに関する推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca1aeed0ad8c80cc32d333aeef37d1da6feabfc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-security-recommendations"></a><span data-ttu-id="649d4-102">SMTP アダプタのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="649d4-102">SMTP Adapter Security Recommendations</span></span>
<span data-ttu-id="649d4-103">SMTP アダプタは、BizTalk Server を実行しているサーバーと他のアプリケーション間で簡易メール転送プロトコル (SMTP) を介して情報を交換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="649d4-103">You use the SMTP adapter to exchange information between a server running BizTalk Server and other applications by means of the Simple Mail Transfer Protocol (SMTP) protocol.</span></span> <span data-ttu-id="649d4-104">BizTalk Server から他のアプリケーションにメッセージを送信するには、電子メール メッセージを作成し、指定した電子メール アドレスに配信します。</span><span class="sxs-lookup"><span data-stu-id="649d4-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="649d4-105">SMTP アダプタは、メッセージの送信のみに使用できます。</span><span class="sxs-lookup"><span data-stu-id="649d4-105">You can use the SMTP adapter only for sending messages.</span></span> <span data-ttu-id="649d4-106">SMTP アダプターに関する詳細については、次を参照してください。 [SMTP アダプター](../core/smtp-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="649d4-106">For more information about the SMTP adapter, see [SMTP Adapter](../core/smtp-adapter.md).</span></span>  
  
 <span data-ttu-id="649d4-107">SMTP アダプタを実行しているホスト インスタンス用のサービス アカウントを構成する場合、リモートの SMTP サーバーで使用する認証の種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="649d4-107">When you configure the service account for the host instance running the SMTP adapter, you need to specify the type of authentication you want to use with the remote SMTP server.</span></span> <span data-ttu-id="649d4-108">認証オプションには、基本認証 (クリア テキスト)、NTLM (現在の資格情報を使用) があります。SMTP サーバーで認証が不要な場合には指定しません。</span><span class="sxs-lookup"><span data-stu-id="649d4-108">The authentication options are basic authentication (clear text), NTLM (by using current credentials), or none if authentication is not required by the SMTP server.</span></span>  
  
 <span data-ttu-id="649d4-109">SMTP アダプタを使用してメッセージを送信する場合、既定では、メッセージはクリア テキストで送信されます。</span><span class="sxs-lookup"><span data-stu-id="649d4-109">When you send a message by using the SMTP adapter, BizTalk Server sends the message in clear text by default.</span></span> <span data-ttu-id="649d4-110">S/MIME エンコーダ コンポーネントのあるパイプラインを使用する場合、メッセージは暗号化してから SMTP サーバーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="649d4-110">If you use a pipeline that has an S/MIME encoder component, you can encrypt the message before you send it to the SMTP server.</span></span> <span data-ttu-id="649d4-111">ただし、SMTP ヘッダーはクリア テキストのままです。</span><span class="sxs-lookup"><span data-stu-id="649d4-111">However, the SMTP header is still in clear text.</span></span>  
  
 <span data-ttu-id="649d4-112">BizTalk Server から送信される電子メール メッセージを監査する場合、SMTP アダプタを使用して、独自の SMTP サーバーに接続する必要があります。接続したら、メッセージを監査できるようになります。</span><span class="sxs-lookup"><span data-stu-id="649d4-112">If you want to audit the e-mail messages that BizTalk Server sends, you should use the SMTP adapter to connect to your own SMTP server, where you can then audit the messages.</span></span>  
  
 <span data-ttu-id="649d4-113">SMTP アダプタは、Secure Sockets Layer (SSL) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="649d4-113">The SMTP adapter does not support Secure Sockets Layer (SSL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="649d4-114">参照</span><span class="sxs-lookup"><span data-stu-id="649d4-114">See Also</span></span>  
 <span data-ttu-id="649d4-115">[受信と送信サーバーのポート](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="649d4-115">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="649d4-116">セキュリティの最小ユーザー権限</span><span class="sxs-lookup"><span data-stu-id="649d4-116">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)