---
title: SMTP アダプタのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b89406529c2a112d667888a67df02e9ab9a693
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314409"
---
# <a name="smtp-adapter-security-recommendations"></a><span data-ttu-id="5f99b-102">SMTP アダプタのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5f99b-102">SMTP Adapter Security Recommendations</span></span>
<span data-ttu-id="5f99b-103">簡易メール転送プロトコル (SMTP) プロトコルを使用して BizTalk Server と他のアプリケーションを実行するサーバーの間で情報を交換するのにには、SMTP アダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f99b-103">You use the SMTP adapter to exchange information between a server running BizTalk Server and other applications by means of the Simple Mail Transfer Protocol (SMTP) protocol.</span></span> <span data-ttu-id="5f99b-104">BizTalk Server は、電子メール メッセージを作成し、指定した電子メール アドレスに配信して、他のアプリケーションにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="5f99b-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="5f99b-105">SMTP アダプタは、メッセージの送信のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f99b-105">You can use the SMTP adapter only for sending messages.</span></span> <span data-ttu-id="5f99b-106">SMTP アダプターに関する詳細については、次を参照してください。 [SMTP アダプター](../core/smtp-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="5f99b-106">For more information about the SMTP adapter, see [SMTP Adapter](../core/smtp-adapter.md).</span></span>  
  
 <span data-ttu-id="5f99b-107">SMTP アダプタを実行するホスト インスタンスのサービス アカウントを構成するときに、リモートの SMTP サーバーで使用する認証の種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f99b-107">When you configure the service account for the host instance running the SMTP adapter, you need to specify the type of authentication you want to use with the remote SMTP server.</span></span> <span data-ttu-id="5f99b-108">認証オプションは、SMTP サーバーで認証が不要な場合は基本認証 (クリア テキスト)、NTLM (を現在の資格情報を使用)、または none。</span><span class="sxs-lookup"><span data-stu-id="5f99b-108">The authentication options are basic authentication (clear text), NTLM (by using current credentials), or none if authentication is not required by the SMTP server.</span></span>  
  
 <span data-ttu-id="5f99b-109">SMTP アダプターを使用してメッセージを送信するときに BizTalk Server は、既定ではクリア テキストでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5f99b-109">When you send a message by using the SMTP adapter, BizTalk Server sends the message in clear text by default.</span></span> <span data-ttu-id="5f99b-110">S/MIME エンコーダー コンポーネントを含むパイプラインを使用する場合は、SMTP サーバーに送信する前に、メッセージを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="5f99b-110">If you use a pipeline that has an S/MIME encoder component, you can encrypt the message before you send it to the SMTP server.</span></span> <span data-ttu-id="5f99b-111">ただし、SMTP ヘッダーはクリア テキストです。</span><span class="sxs-lookup"><span data-stu-id="5f99b-111">However, the SMTP header is still in clear text.</span></span>  
  
 <span data-ttu-id="5f99b-112">BizTalk Server が送信する電子メール メッセージを監査する場合は、する必要がありますアダプターを使用する、SMTP、独自の SMTP サーバーへの接続にメッセージを監査できます。</span><span class="sxs-lookup"><span data-stu-id="5f99b-112">If you want to audit the e-mail messages that BizTalk Server sends, you should use the SMTP adapter to connect to your own SMTP server, where you can then audit the messages.</span></span>  
  
 <span data-ttu-id="5f99b-113">SMTP アダプタは、Secure Sockets Layer (SSL) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5f99b-113">The SMTP adapter does not support Secure Sockets Layer (SSL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f99b-114">参照</span><span class="sxs-lookup"><span data-stu-id="5f99b-114">See Also</span></span>  
 <span data-ttu-id="5f99b-115">[受信と送信サーバーのポート](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="5f99b-115">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="5f99b-116">セキュリティ保護のための最小ユーザー権限</span><span class="sxs-lookup"><span data-stu-id="5f99b-116">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)