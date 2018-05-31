---
title: メッセージの InfoPath テンプレート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b8ec04d16da25f39060540aa8a8205421397d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295146"
---
# <a name="the-infopath-message-template"></a><span data-ttu-id="33f8c-102">InfoPath メッセージ テンプレート</span><span class="sxs-lookup"><span data-stu-id="33f8c-102">The InfoPath Message Template</span></span>
<span data-ttu-id="33f8c-103">ESB の管理ポータルで ESB フォールト メッセージを表示する代わりに、ユーザーの利用できますで提供される、ESB 例外メッセージ ビューアーをという名前の Microsoft InfoPath メッセージ テンプレート、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="33f8c-103">As an alternative to viewing ESB fault messages in the ESB Management Portal, users can take advantage of a Microsoft InfoPath message template named the ESB Exception Message Viewer, provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="33f8c-104">ESB 例外管理フレームワークは、ESB 例外メッセージ ビューアー テンプレートと共に表示されるエラー メッセージと元のメッセージが含まれているいくつかのビューをシリアル化された形式でメッセージを保持できます。</span><span class="sxs-lookup"><span data-stu-id="33f8c-104">The ESB Exception Management Framework can persist messages in a serialized format that, together with the ESB Exception Message Viewer template, will display several views of the fault message and the original messages it contains.</span></span> <span data-ttu-id="33f8c-105">ESB 例外メッセージ ビューアーには、次のビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="33f8c-105">The ESB Exception Message Viewer provides the following views:</span></span>  
  
-   <span data-ttu-id="33f8c-106">全般ビュー</span><span class="sxs-lookup"><span data-stu-id="33f8c-106">General view</span></span>  
  
-   <span data-ttu-id="33f8c-107">例外オブジェクトの表示</span><span class="sxs-lookup"><span data-stu-id="33f8c-107">Exception Object view</span></span>  
  
-   <span data-ttu-id="33f8c-108">メッセージ ビュー</span><span class="sxs-lookup"><span data-stu-id="33f8c-108">Messages view</span></span>  
  
 <span data-ttu-id="33f8c-109">図 1 は、例外の最もアンビエント プロパティを表示する ESB 例外メッセージ ビューアーの [全般] ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="33f8c-109">Figure 1 shows the General view of the ESB Exception Message Viewer, which displays most ambient properties of the exception.</span></span>  
  
 <span data-ttu-id="33f8c-110">![例外メッセージの全般ビュー](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4 ExceptionMessageGeneralView")</span><span class="sxs-lookup"><span data-stu-id="33f8c-110">![Exception Message General View](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")</span></span>  
  
 <span data-ttu-id="33f8c-111">**図 1**</span><span class="sxs-lookup"><span data-stu-id="33f8c-111">**Figure 1**</span></span>  
  
 <span data-ttu-id="33f8c-112">**[全般] ビューを表示、ESB 例外メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="33f8c-112">**The ESB Exception Message Viewer showing the General view**</span></span>  
  
 <span data-ttu-id="33f8c-113">図 2 は、例外オブジェクト ビューのプロパティとからスタック トレースが表示されます、 **System.Exception**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="33f8c-113">Figure 2 shows the Exception Object view, which displays the properties and the stack trace from the **System.Exception** object.</span></span>  
  
 <span data-ttu-id="33f8c-114">![例外メッセージ、例外オブジェクト](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4 ExceptionMessageExceptionObject")</span><span class="sxs-lookup"><span data-stu-id="33f8c-114">![Exception Message Exception Object](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")</span></span>  
  
 <span data-ttu-id="33f8c-115">**図 2**</span><span class="sxs-lookup"><span data-stu-id="33f8c-115">**Figure 2**</span></span>  
  
 <span data-ttu-id="33f8c-116">**例外オブジェクトのビューを表示、ESB 例外メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="33f8c-116">**The ESB Exception Message Viewer showing the Exception Object view**</span></span>  
  
 <span data-ttu-id="33f8c-117">図 3 は、元のユーザーが使用可能な永続化されたメッセージから選択できるドロップダウン リストを提供するメッセージ ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="33f8c-117">Figure 3 shows the Messages view, which provides a drop-down list from which the user can select from available persisted messages.</span></span> <span data-ttu-id="33f8c-118">ビューには、永続化されたメッセージと XML メッセージの内容のコンテキスト プロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33f8c-118">The view displays the values of the context properties of the persisted message and the XML message content.</span></span>  
  
 <span data-ttu-id="33f8c-119">![例外、メッセージのメッセージ ビュー](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4 ExceptionMessageMessagesView")</span><span class="sxs-lookup"><span data-stu-id="33f8c-119">![Exception Message Messages View](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")</span></span>  
  
 <span data-ttu-id="33f8c-120">**図 3**</span><span class="sxs-lookup"><span data-stu-id="33f8c-120">**Figure 3**</span></span>  
  
 <span data-ttu-id="33f8c-121">**メッセージ ビューを表示、ESB 例外メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="33f8c-121">**The ESB Exception Message Viewer showing the Messages view**</span></span>