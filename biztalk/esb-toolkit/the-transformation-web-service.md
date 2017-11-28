---
title: "変換の Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abad7a5a7bae3c76fba58ecd92fc3384df5ca25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-transformation-web-service"></a><span data-ttu-id="e5300-102">変換の Web サービス</span><span class="sxs-lookup"><span data-stu-id="e5300-102">The Transformation Web Service</span></span>
<span data-ttu-id="e5300-103">変換の Web サービスでは、外部アプリケーションを ESB アプリケーションにドキュメントを送信し、展開された Microsoft BizTalk マップを使用して変換を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5300-103">The Transformation Web service enables external applications to submit a document to an ESB application and have it transformed using a deployed Microsoft BizTalk map.</span></span> <span data-ttu-id="e5300-104">変換エージェントとは異なり、このサービスは、BizTalk メッセージ ボックス データベースを経由してメッセージをルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="e5300-104">Unlike the transformation agent, this service does not route messages through the BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="e5300-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています: ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) バージョン。</span><span class="sxs-lookup"><span data-stu-id="e5300-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="e5300-106">サービス名は**ESB です。TransformServices**と**ESB です。TransformServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="e5300-106">The service names are **ESB.TransformServices** and **ESB.TransformServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="e5300-107">**変換します。**</span><span class="sxs-lookup"><span data-stu-id="e5300-107">**Transform.**</span></span> <span data-ttu-id="e5300-108">このメソッドは、パラメーターとして、**文字列**を変換するメッセージを格納していると、**文字列**BizTalk に展開されているマップの完全修飾名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="e5300-108">This method takes as parameters a **String** that contains the message to transform and a **String** that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="e5300-109">このメソッドを返します、**文字列**変換されたドキュメントを格納しています。</span><span class="sxs-lookup"><span data-stu-id="e5300-109">The method returns a **String** that contains the transformed document.</span></span> <span data-ttu-id="e5300-110">文字列パラメーターの使用は、異機種混在環境での相互運用性のリスクを軽減します。ただし、これによって、Web サービス (biztalk 変換サービスがより適してサイズの大きいドキュメント) 大きなドキュメントの変換に使用しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5300-110">The use of string parameters reduces the risk of interoperability issues in a heterogeneous environment; however, keep in mind that this is a Web service, so you should avoid using it to transform large documents (the Transformation Service in BizTalk is better suited for large documents).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5300-111">既定では、変換の Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="e5300-111">By default, the Transformation Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="e5300-112">クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec および適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。</span><span class="sxs-lookup"><span data-stu-id="e5300-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>