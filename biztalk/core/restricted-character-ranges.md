---
title: "文字範囲を制限する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74f1399aaa828d5c23c2600ebabeb7063a982447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restricted-character-ranges"></a><span data-ttu-id="02ce7-102">文字範囲の制限</span><span class="sxs-lookup"><span data-stu-id="02ce7-102">Restricted Character Ranges</span></span>

## <a name="overview"></a><span data-ttu-id="02ce7-103">概要</span><span class="sxs-lookup"><span data-stu-id="02ce7-103">Overview</span></span>
<span data-ttu-id="02ce7-104">フラット ファイル メッセージのスキーマを作成する場合、特定の文字または文字範囲が送信メッセージに格納されないよう [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に指示を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="02ce7-104">When creating a schema for flat file messages, you can direct [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to block a particular character or a range of characters from being included in any outgoing message.</span></span> <span data-ttu-id="02ce7-105">これを行うには、BizTalk エディターで、送信先スキーマとして使用されるスキーマを開きます。</span><span class="sxs-lookup"><span data-stu-id="02ce7-105">To do this, in BizTalk Editor, open a schema that is to be used as a destination schema.</span></span> <span data-ttu-id="02ce7-106">選択、**スキーマ**ノードと、使用、**文字の制限**プロパティを開くには、**文字の制限** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="02ce7-106">Select the **Schema** node and the use the **Restricted Characters** property to open the **Restricted Characters** dialog box.</span></span> <span data-ttu-id="02ce7-107">範囲をできないようにする BizTalk Server によって送信されるメッセージに含まれる文字を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="02ce7-107">Enter the character range(s) that you want to prevent being included in any message sent by BizTalk Server, and then click **OK**.</span></span> <span data-ttu-id="02ce7-108">BizTalk Server がで指定された文字を処理しようとしたときに、**文字の制限**処理が停止し、エラー メッセージを送信先スキーマのダイアログ ボックスを生成します。</span><span class="sxs-lookup"><span data-stu-id="02ce7-108">Whenever BizTalk Server attempts to process a character specified in the **Restricted Characters** dialog box of a destination schema, processing stops and an error message is generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02ce7-109">BizTalk Server の文字範囲の制限は、フラット ファイル拡張子の機能です。このため、XML メッセージには適用されません。</span><span class="sxs-lookup"><span data-stu-id="02ce7-109">In BizTalk Server, character range restriction is a function of the Flat File Extension, and as such, does not apply to XML messages.</span></span> <span data-ttu-id="02ce7-110">さまざまな種類のメッセージに今後提供される可能性のある拡張機能は、対応するメッセージ形式の文字範囲の制限の実装方法によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02ce7-110">Extensions that might be offered in the future for different types of messages might differ in how they implement character range restriction for their supported message formats.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ce7-111">参照</span><span class="sxs-lookup"><span data-stu-id="02ce7-111">See Also</span></span>  
-  [<span data-ttu-id="02ce7-112">ファイル メッセージ スキーマをフラットを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="02ce7-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)   
-  <span data-ttu-id="02ce7-113">**文字の制限 (フラット ファイル スキーマのノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="02ce7-113">**Restricted Characters (Node Property of Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>