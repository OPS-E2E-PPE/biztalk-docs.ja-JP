---
title: EDI ソリューションのアーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 9df4d308af97e0fcccf52d2c6f42660afa7cf079
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350252"
---
# <a name="edi-solution-architecture"></a><span data-ttu-id="2b44e-102">EDI ソリューションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2b44e-102">EDI Solution Architecture</span></span>
<span data-ttu-id="2b44e-103">電子データ交換 (EDI) では、ビジネス エンティティ データ交換を電子的に最も一般的な手段の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="2b44e-103">Electronic Data Interchange (EDI) is one of the most prevalent means by which business entities exchange data electronically.</span></span> <span data-ttu-id="2b44e-104">メッセージの構文や標準 (ANSI X12、UN/EDIFACT など)、メッセージング プロトコル、およびトランスポート EDI を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b44e-104">EDI usage entails message syntax and standards (including ANSI X12 and UN/EDIFACT), messaging protocol, and transports.</span></span> <span data-ttu-id="2b44e-105">次に、EDI メッセージングの特性を示します。</span><span class="sxs-lookup"><span data-stu-id="2b44e-105">The following are characteristics of EDI messaging:</span></span>  
  
- <span data-ttu-id="2b44e-106">データは、常に、想定どおりに到着して破損しているか正しくないデータが自動的に検出され、報告される EDI メッセージング プロトコルを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b44e-106">EDI messaging protocols ensure that data always arrives as expected, and corrupted or incorrect data is automatically detected and reported.</span></span>  
  
- <span data-ttu-id="2b44e-107">EDI のメカニズムは、通常、データ集計のスキーマ (バッチ処理) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b44e-107">EDI mechanisms usually specify data aggregation schemes (batching).</span></span>  
  
- <span data-ttu-id="2b44e-108">ユーザーは、プロパティのサブセットまたは EDI ガイドラインの特定の実装を実装することで多くの場合、EDI ドキュメント定義をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2b44e-108">Users often customize EDI document definitions by implementing subset or specific implementation of an EDI guideline.</span></span>  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2b44e-109">使用して EDI メッセージを処理では、受信し、解析と EDI メッセージをシリアル化を実行できる EDI 送信パイプラインを特定します。</span><span class="sxs-lookup"><span data-stu-id="2b44e-109">processes EDI messages using receive and send pipelines specific to EDI that can parse and serialize EDI messages.</span></span> <span data-ttu-id="2b44e-110">このセクションでの EDI ソリューションのアーキテクチャを説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、受信側と送信側の処理、メッセージの検証、および状態レポートの詳細を含めています。</span><span class="sxs-lookup"><span data-stu-id="2b44e-110">This section describes the architecture of EDI solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including specifics of receive-side and send-side processing, message validation, and status reporting.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b44e-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2b44e-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2b44e-112">EDI メッセージング</span><span class="sxs-lookup"><span data-stu-id="2b44e-112">EDI Messaging</span></span>](../core/edi-messaging.md)  
  
-   [<span data-ttu-id="2b44e-113">EDI 処理におけるアグリーメントのロール</span><span class="sxs-lookup"><span data-stu-id="2b44e-113">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [<span data-ttu-id="2b44e-114">BizTalk Server が EDI メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="2b44e-114">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [<span data-ttu-id="2b44e-115">BizTalk Server が EDI メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="2b44e-115">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [<span data-ttu-id="2b44e-116">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="2b44e-116">EDI Message Validation</span></span>](../core/edi-message-validation.md)  
  
-   [<span data-ttu-id="2b44e-117">XML ツール拡張機能の使用</span><span class="sxs-lookup"><span data-stu-id="2b44e-117">Using the XML Tool Extensions</span></span>](../core/using-the-xml-tool-extensions.md)