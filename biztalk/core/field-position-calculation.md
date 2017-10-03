---
title: "位置の計算フィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c58f532ea64300518667d677d2248f5c1c2b6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="field-position-calculation"></a><span data-ttu-id="112f8-102">フィールド位置の計算</span><span class="sxs-lookup"><span data-stu-id="112f8-102">Field Position Calculation</span></span>

## <a name="overview"></a><span data-ttu-id="112f8-103">概要</span><span class="sxs-lookup"><span data-stu-id="112f8-103">Overview</span></span>
<span data-ttu-id="112f8-104">使用すると、**位置指定値**と**位置指定オフセット**のプロパティ、**フィールド要素**と**フィールド属性**内のノード、フラット ファイル メッセージの位置指定レコードのレイアウトを定義するスキーマ、**開始位置**と**長さ**の列、**フラット ファイル** タブBizTalk エディターを表示する計算の開始位置と長さ、それぞれの関連するフィールドとレコード。</span><span class="sxs-lookup"><span data-stu-id="112f8-104">When you use the **Positional Length** and **Positional Offset** properties of the **Field Element** and **Field Attribute** nodes in your schema to define the layout of the positional records in your flat file message, the **Start Position** and **Length** columns of the **Flat File** tab in BizTalk Editor show the calculated starting positions and lengths, respectively, of the relevant fields and records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="112f8-105">**フラット ファイル**フラット ファイル拡張機能を使用して、構成した場合、BizTalk エディターで XSD ビューの代替タブ付きビューとして タブが表示されます、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="112f8-105">The **Flat File** tab appear as an alternate tabbed view with the XSD view in BizTalk Editor when you have configured the flat file extension using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="112f8-106">このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="112f8-106">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="112f8-107">一般に、特定のフィールドの開始位置*N*前のフィールドの開始位置と前のフィールドとフィールドの指定した (位置指定) オフセットの長さは、 *N*.</span><span class="sxs-lookup"><span data-stu-id="112f8-107">In general, the starting position of a particular field *N* is the starting position of the previous field, plus the length of the previous field, plus the (positional) offset you have specified for field *N*.</span></span>  
  
 <span data-ttu-id="112f8-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のすべてのフィールド位置の計算は、自動的にまとめて行われるので、コマンドを実行する必要はありません (以前のバージョンの BizTalk Server では、コマンドを実行していました)。</span><span class="sxs-lookup"><span data-stu-id="112f8-108">All field position calculation in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is performed automatically, on-the-fly, without any need to execute a command (as was required in previous versions of BizTalk Server).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="112f8-109">参照</span><span class="sxs-lookup"><span data-stu-id="112f8-109">See Also</span></span>  
-  [<span data-ttu-id="112f8-110">位置指定レコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="112f8-110">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
-  <span data-ttu-id="112f8-111">**位置指定値 (フラット ファイル スキーマのノード プロパティ)**と**位置指定オフセット (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="112f8-111">**Positional Length (Node Property of Flat File Schemas)** and **Positional Offset (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>