---
title: OrchestrationEventStream |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7c63610-6344-4b71-8d65-3add7883bc79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981f21440f7634fc2444f850c9b10766ae4a636b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262967"
---
# <a name="orchestrationeventstream"></a><span data-ttu-id="910f4-102">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="910f4-102">OrchestrationEventStream</span></span>
<span data-ttu-id="910f4-103">OrchestrationEventStream (OES) API は、BizTalk Server がインストールされているコンピューターでアプリケーションを実行し、BizTalk オーケストレーション トランザクションの一部である項目を追跡する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="910f4-103">You use the OrchestrationEventStream (OES) API when your application runs on a computer on which BizTalk Server is installed and you are tracking items that are part of BizTalk orchestration transactions.</span></span>  
  
 <span data-ttu-id="910f4-104">OES API は、追跡データを最初に BizTalk メッセージ ボックス データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="910f4-104">The OES API stores tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="910f4-105">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="910f4-105">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="910f4-106">OES API は、Microsoft.BizTalk.Bam.EventObservation 名前空間に含まれています。</span><span class="sxs-lookup"><span data-stu-id="910f4-106">The OES API is found in the Microsoft.BizTalk.Bam.EventObservation namespace.</span></span> <span data-ttu-id="910f4-107">API を使用するには、Microsoft.Biztalk.BAM.Xlangs.dll をプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910f4-107">To use the API you must add the Microsoft.Biztalk.BAM.Xlangs.dll to your project.</span></span>  
  
## <a name="oes-members"></a><span data-ttu-id="910f4-108">OES のメンバー</span><span class="sxs-lookup"><span data-stu-id="910f4-108">OES Members</span></span>  
 <span data-ttu-id="910f4-109">OES API は、 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="910f4-109">The OES API is derived from the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) class.</span></span>  
  
 <span data-ttu-id="910f4-110">OES は、EventStream クラスのメソッドをすべて実装していますが、動作に関して以下の例外があります。</span><span class="sxs-lookup"><span data-stu-id="910f4-110">OES implements all of the methods within the EventStream class, but has the  following exception in behaviors:</span></span>  
  
 <span data-ttu-id="910f4-111">**パブリック静的 void Clear();**</span><span class="sxs-lookup"><span data-stu-id="910f4-111">**public static void Clear();**</span></span>  
  
 <span data-ttu-id="910f4-112">操作なし</span><span class="sxs-lookup"><span data-stu-id="910f4-112">No operation.</span></span>  
  
 <span data-ttu-id="910f4-113">**public static void Flush();**</span><span class="sxs-lookup"><span data-stu-id="910f4-113">**public static void Flush();**</span></span>  
  
 <span data-ttu-id="910f4-114">操作なし</span><span class="sxs-lookup"><span data-stu-id="910f4-114">No operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910f4-115">参照</span><span class="sxs-lookup"><span data-stu-id="910f4-115">See Also</span></span>  
 [<span data-ttu-id="910f4-116">EventStream クラス</span><span class="sxs-lookup"><span data-stu-id="910f4-116">EventStream Classes</span></span>](../core/eventstream-classes.md)