---
title: 文字範囲の制限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: add7cfdf529d21c7ed54ae60d1c39c39266af6fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255112"
---
# <a name="restricted-character-ranges"></a><span data-ttu-id="9c148-102">文字範囲の制限</span><span class="sxs-lookup"><span data-stu-id="9c148-102">Restricted Character Ranges</span></span>

## <a name="overview"></a><span data-ttu-id="9c148-103">概要</span><span class="sxs-lookup"><span data-stu-id="9c148-103">Overview</span></span>
<span data-ttu-id="9c148-104">フラット ファイル メッセージのスキーマを作成するときに指示できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定の文字または送信メッセージに含まれている文字の範囲をブロックします。</span><span class="sxs-lookup"><span data-stu-id="9c148-104">When creating a schema for flat file messages, you can direct [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to block a particular character or a range of characters from being included in any outgoing message.</span></span> <span data-ttu-id="9c148-105">BizTalk エディターで、これは、送信先スキーマとして使用するスキーマを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c148-105">To do this, in BizTalk Editor, open a schema that is to be used as a destination schema.</span></span> <span data-ttu-id="9c148-106">選択、**スキーマ**ノードと、使用して、**文字の制限**プロパティを開き、**文字の制限** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9c148-106">Select the **Schema** node and the use the **Restricted Characters** property to open the **Restricted Characters** dialog box.</span></span> <span data-ttu-id="9c148-107">範囲をできないようにする BizTalk Server によって送信されたメッセージに含まれる文字を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c148-107">Enter the character range(s) that you want to prevent being included in any message sent by BizTalk Server, and then click **OK**.</span></span> <span data-ttu-id="9c148-108">BizTalk Server がで指定された文字を処理しようとしたときに、**文字の制限**の処理が停止し、エラー メッセージを送信先スキーマ ダイアログ ボックスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c148-108">Whenever BizTalk Server attempts to process a character specified in the **Restricted Characters** dialog box of a destination schema, processing stops and an error message is generated.</span></span>  

> [!NOTE]
>  <span data-ttu-id="9c148-109">BizTalk server の文字範囲の制限は、フラット ファイル拡張子の関数であり、XML メッセージには適用されません。</span><span class="sxs-lookup"><span data-stu-id="9c148-109">In BizTalk Server, character range restriction is a function of the Flat File Extension, and as such, does not apply to XML messages.</span></span> <span data-ttu-id="9c148-110">文字範囲の制限、サポートされているメッセージ形式の実装方法が異なるさまざまな種類のメッセージを今後提供される可能性の拡張機能。</span><span class="sxs-lookup"><span data-stu-id="9c148-110">Extensions that might be offered in the future for different types of messages might differ in how they implement character range restriction for their supported message formats.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c148-111">参照</span><span class="sxs-lookup"><span data-stu-id="9c148-111">See Also</span></span>  
- [<span data-ttu-id="9c148-112">フラット ファイル メッセージ スキーマを作成する上での注意点</span><span class="sxs-lookup"><span data-stu-id="9c148-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)   
- <span data-ttu-id="9c148-113">**文字の制限 (フラット ファイル スキーマのノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9c148-113">**Restricted Characters (Node Property of Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
