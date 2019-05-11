---
title: InfoPath メッセージ テンプレート |Microsoft Docs
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
ms.openlocfilehash: 8972c27a433755a922cdc1d5074902e412a46602
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399746"
---
# <a name="the-infopath-message-template"></a><span data-ttu-id="c7aaf-102">InfoPath メッセージ テンプレート</span><span class="sxs-lookup"><span data-stu-id="c7aaf-102">The InfoPath Message Template</span></span>
<span data-ttu-id="c7aaf-103">ESB 管理ポータルで ESB エラー メッセージを表示する代わりに、ユーザーを利用して Microsoft InfoPath メッセージ テンプレートが付属、ESB 例外メッセージ ビューアーを名前付きの[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-103">As an alternative to viewing ESB fault messages in the ESB Management Portal, users can take advantage of a Microsoft InfoPath message template named the ESB Exception Message Viewer, provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="c7aaf-104">ESB 例外管理フレームワークは、ESB 例外メッセージ ビューアー テンプレートと共に、エラー メッセージの元のメッセージが含まれているいくつかのビューが表示されますが、シリアル化された形式でメッセージを保持できます。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-104">The ESB Exception Management Framework can persist messages in a serialized format that, together with the ESB Exception Message Viewer template, will display several views of the fault message and the original messages it contains.</span></span> <span data-ttu-id="c7aaf-105">ESB 例外のメッセージ ビューアーには、次のビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-105">The ESB Exception Message Viewer provides the following views:</span></span>  
  
- <span data-ttu-id="c7aaf-106">[全般] ビュー</span><span class="sxs-lookup"><span data-stu-id="c7aaf-106">General view</span></span>  
  
- <span data-ttu-id="c7aaf-107">例外オブジェクトのビュー</span><span class="sxs-lookup"><span data-stu-id="c7aaf-107">Exception Object view</span></span>  
  
- <span data-ttu-id="c7aaf-108">メッセージ ビュー</span><span class="sxs-lookup"><span data-stu-id="c7aaf-108">Messages view</span></span>  
  
  <span data-ttu-id="c7aaf-109">図 1 は、例外の最もアンビエント プロパティを表示する ESB 例外メッセージ ビューアの [全般] ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-109">Figure 1 shows the General view of the ESB Exception Message Viewer, which displays most ambient properties of the exception.</span></span>  
  
  <span data-ttu-id="c7aaf-110">![例外メッセージの全般ビュー](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4 ExceptionMessageGeneralView")</span><span class="sxs-lookup"><span data-stu-id="c7aaf-110">![Exception Message General View](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")</span></span>  
  
  <span data-ttu-id="c7aaf-111">**図 1**</span><span class="sxs-lookup"><span data-stu-id="c7aaf-111">**Figure 1**</span></span>  
  
  <span data-ttu-id="c7aaf-112">**[全般] ビューを表示、ESB 例外メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="c7aaf-112">**The ESB Exception Message Viewer showing the General view**</span></span>  
  
  <span data-ttu-id="c7aaf-113">図 2 は、プロパティとからのスタック トレースを表示する例外オブジェクトのビューを示しています、 **System.Exception**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-113">Figure 2 shows the Exception Object view, which displays the properties and the stack trace from the **System.Exception** object.</span></span>  
  
  <span data-ttu-id="c7aaf-114">![例外メッセージ、例外オブジェクト](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4 ExceptionMessageExceptionObject")</span><span class="sxs-lookup"><span data-stu-id="c7aaf-114">![Exception Message Exception Object](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")</span></span>  
  
  <span data-ttu-id="c7aaf-115">**図 2**</span><span class="sxs-lookup"><span data-stu-id="c7aaf-115">**Figure 2**</span></span>  
  
  <span data-ttu-id="c7aaf-116">**例外オブジェクトのビューを表示、ESB 例外メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="c7aaf-116">**The ESB Exception Message Viewer showing the Exception Object view**</span></span>  
  
  <span data-ttu-id="c7aaf-117">図 3 は、元となる、ユーザーは、使用可能な永続化されたメッセージから選択できるドロップダウン リストを提供するメッセージ ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-117">Figure 3 shows the Messages view, which provides a drop-down list from which the user can select from available persisted messages.</span></span> <span data-ttu-id="c7aaf-118">ビューには、永続化されたメッセージと XML メッセージの内容のコンテキスト プロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7aaf-118">The view displays the values of the context properties of the persisted message and the XML message content.</span></span>  
  
  <span data-ttu-id="c7aaf-119">![例外のメッセージのメッセージ ビュー](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4 ExceptionMessageMessagesView")</span><span class="sxs-lookup"><span data-stu-id="c7aaf-119">![Exception Message Messages View](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")</span></span>  
  
  <span data-ttu-id="c7aaf-120">**図 3**</span><span class="sxs-lookup"><span data-stu-id="c7aaf-120">**Figure 3**</span></span>  
  
  <span data-ttu-id="c7aaf-121">**メッセージ ビューを表示、ESB 例外メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="c7aaf-121">**The ESB Exception Message Viewer showing the Messages view**</span></span>