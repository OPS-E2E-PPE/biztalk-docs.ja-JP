---
title: EDI ソリューションのアーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42afbb604a8cef1387418e175a39150f0182c607
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239882"
---
# <a name="edi-solution-architecture"></a><span data-ttu-id="4bfc7-102">EDI ソリューションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="4bfc7-102">EDI Solution Architecture</span></span>
<span data-ttu-id="4bfc7-103">電子データ交換 (EDI) は、ビジネス エンティティがデータを電子的に交換するために最も広く使用されている方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-103">Electronic Data Interchange (EDI) is one of the most prevalent means by which business entities exchange data electronically.</span></span> <span data-ttu-id="4bfc7-104">EDI を使用するには、メッセージの構文や標準 (ANSI X12、UN/EDIFACT など)、メッセージング プロトコル、およびトランスポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-104">EDI usage entails message syntax and standards (including ANSI X12 and UN/EDIFACT), messaging protocol, and transports.</span></span> <span data-ttu-id="4bfc7-105">EDI によるメッセージングには、次のような特性があります。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-105">The following are characteristics of EDI messaging:</span></span>  
  
-   <span data-ttu-id="4bfc7-106">EDI のメッセージング プロトコルにより、データが常に期待どおりに配信され、破損したデータや正しくないデータが自動的に検出および報告されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-106">EDI messaging protocols ensure that data always arrives as expected, and corrupted or incorrect data is automatically detected and reported.</span></span>  
  
-   <span data-ttu-id="4bfc7-107">EDI のメカニズムでは、通常、データ集計スキーマ (バッチ処理) が指定されています。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-107">EDI mechanisms usually specify data aggregation schemes (batching).</span></span>  
  
-   <span data-ttu-id="4bfc7-108">EDI ガイドラインのサブセットや特定の実装を組み込むことにより、EDI のドキュメント定義をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-108">Users often customize EDI document definitions by implementing subset or specific implementation of an EDI guideline.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4bfc7-109"> は、EDI メッセージの解析とシリアル化を実行できる EDI 専用の受信パイプラインと送信パイプラインを使用して EDI メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-109"> processes EDI messages using receive and send pipelines specific to EDI that can parse and serialize EDI messages.</span></span> <span data-ttu-id="4bfc7-110">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における EDI ソリューションのアーキテクチャ (受信側および送信側の処理に関する詳細、メッセージの検証、状態レポートなど) について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bfc7-110">This section describes the architecture of EDI solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including specifics of receive-side and send-side processing, message validation, and status reporting.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bfc7-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4bfc7-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4bfc7-112">EDI メッセージング</span><span class="sxs-lookup"><span data-stu-id="4bfc7-112">EDI Messaging</span></span>](../core/edi-messaging.md)  
  
-   [<span data-ttu-id="4bfc7-113">EDI 処理におけるアグリーメントのロール</span><span class="sxs-lookup"><span data-stu-id="4bfc7-113">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [<span data-ttu-id="4bfc7-114">BizTalk Server が EDI メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="4bfc7-114">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [<span data-ttu-id="4bfc7-115">BizTalk Server が EDI メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="4bfc7-115">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [<span data-ttu-id="4bfc7-116">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="4bfc7-116">EDI Message Validation</span></span>](../core/edi-message-validation.md)  
  
-   [<span data-ttu-id="4bfc7-117">XML ツール拡張機能の使用</span><span class="sxs-lookup"><span data-stu-id="4bfc7-117">Using the XML Tool Extensions</span></span>](../core/using-the-xml-tool-extensions.md)