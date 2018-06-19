---
title: Web サービスを公開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Server Web Services Publishing Wizard
ms.assetid: eed0717c-b390-492a-a3b9-ae31024805a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aca08c1e4fabd833bd6de924e04e6052cd99890b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268546"
---
# <a name="publishing-web-services"></a><span data-ttu-id="49c69-102">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="49c69-102">Publishing Web Services</span></span>
<span data-ttu-id="49c69-103">Web サービスを公開すると、Microsoft BizTalk Server にメッセージを送信する Web サービスを作成し、そのサービスをオーケストレーションやその他の送信アダプターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="49c69-103">Publishing Web services enables you to create a Web service that can submit messages to Microsoft BizTalk Server for use by orchestrations and other send adapters.</span></span> <span data-ttu-id="49c69-104">公開された Web サービスを作成するには、BizTalk Web サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="49c69-104">You create published Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="49c69-105">SOAP 送信ハンドラーの構成方法の詳細については、次を参照してください。 [SOAP 送信ハンドラーを構成する方法](../core/how-to-configure-a-soap-send-handler.md)です。</span><span class="sxs-lookup"><span data-stu-id="49c69-105">For information about configuring a SOAP send handler, see [How to Configure a SOAP Send Handler](../core/how-to-configure-a-soap-send-handler.md).</span></span> <span data-ttu-id="49c69-106">SOAP 送信ポートの構成については、次を参照してください。 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="49c69-106">For information about configuring a SOAP send port, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
 <span data-ttu-id="49c69-107">BizTalk Web サービス公開ウィザード Web サービスを公開する 2 つのメソッドを提供します。: Web サービスとしてのオーケストレーションの公開とスキーマを Web サービスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="49c69-107">The BizTalk Web Services Publishing Wizard provides you with two methods to publish Web services: publishing an orchestration as a Web service and publishing schemas as a Web service.</span></span>  
  
 <span data-ttu-id="49c69-108">Microsoft BizTalk Server のオーケストレーションとスキーマを Web サービスとして公開する前に、Microsoft インターネット インフォメーション サービス (IIS) と ASP.NET をインストールして有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49c69-108">You must install and enable Microsoft Internet Information Services (IIS) and ASP.NET before you can publish Microsoft BizTalk Server orchestrations and schemas as Web services.</span></span> <span data-ttu-id="49c69-109">IIS と ASP.NET のインストール方法の詳細については、インストールするインターネット インフォメーション サービス (IIS) にある BizTalk Server インストール ガイドを参照してください[ハイパーリンク"http://go.microsoft.com/fwlink/?。LinkID 191321"http://go.microsoft.com/fwlink/? を =LinkID = 191321](http://go.microsoft.com/fwlink/?LinkID=191321)です。</span><span class="sxs-lookup"><span data-stu-id="49c69-109">For information about installing IIS and ASP.NET, see Installing Internet Information Services (IIS) in the BizTalk Server Installation Guide located at [HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="49c69-110">BizTalk Web サービス公開ウィザードを実行する前に、Web サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49c69-110">Before running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="49c69-111">詳細については、システム用の Web サービスを有効にすると、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="49c69-111">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49c69-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="49c69-112">In This Section</span></span>  
  
-   [<span data-ttu-id="49c69-113">Web サービスを公開するための計画</span><span class="sxs-lookup"><span data-stu-id="49c69-113">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)  
  
-   [<span data-ttu-id="49c69-114">Web サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="49c69-114">Enabling Web Services</span></span>](../core/enabling-web-services.md)  
  
-   [<span data-ttu-id="49c69-115">Web サービスとしてのオーケストレーションの公開</span><span class="sxs-lookup"><span data-stu-id="49c69-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="49c69-116">Web サービスとしてのスキーマの公開</span><span class="sxs-lookup"><span data-stu-id="49c69-116">Publishing Schemas as a Web Service</span></span>](../core/publishing-schemas-as-a-web-service.md)  
  
-   [<span data-ttu-id="49c69-117">Web サービスを公開する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="49c69-117">Considerations When Publishing Web Services</span></span>](../core/considerations-when-publishing-web-services.md)  
  
-   [<span data-ttu-id="49c69-118">公開済み Web サービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="49c69-118">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)  
  
-   [<span data-ttu-id="49c69-119">公開済み Web サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="49c69-119">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)  
  
-   [<span data-ttu-id="49c69-120">非 Visual Studio コンピューターに公開された Web サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="49c69-120">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)