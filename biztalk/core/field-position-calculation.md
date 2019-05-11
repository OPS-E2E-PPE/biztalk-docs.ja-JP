---
title: フィールド位置の計算 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160e28e23de6c792e3669831e84e582dd07c7318
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345591"
---
# <a name="field-position-calculation"></a><span data-ttu-id="85dcb-102">フィールド位置の計算</span><span class="sxs-lookup"><span data-stu-id="85dcb-102">Field Position Calculation</span></span>

## <a name="overview"></a><span data-ttu-id="85dcb-103">概要</span><span class="sxs-lookup"><span data-stu-id="85dcb-103">Overview</span></span>
<span data-ttu-id="85dcb-104">使用すると、**位置指定値**と**位置指定オフセット**のプロパティ、**フィールド要素**と**フィールド属性**内のノード、フラット ファイル メッセージの位置指定レコードのレイアウトを定義するスキーマ、**開始位置**と**長さ**の列、**フラット ファイル**タブBizTalk エディターを表示する、計算の開始位置と長さ、それぞれの関連するフィールドとレコード。</span><span class="sxs-lookup"><span data-stu-id="85dcb-104">When you use the **Positional Length** and **Positional Offset** properties of the **Field Element** and **Field Attribute** nodes in your schema to define the layout of the positional records in your flat file message, the **Start Position** and **Length** columns of the **Flat File** tab in BizTalk Editor show the calculated starting positions and lengths, respectively, of the relevant fields and records.</span></span>  

> [!NOTE]
>  <span data-ttu-id="85dcb-105">**フラット ファイル** タブは、フラット ファイル拡張機能を使用して構成した場合と BizTalk エディターで XSD ビューの代替タブ付きビューとして表示、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="85dcb-105">The **Flat File** tab appear as an alternate tabbed view with the XSD view in BizTalk Editor when you have configured the flat file extension using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="85dcb-106">このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="85dcb-106">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

 <span data-ttu-id="85dcb-107">一般に、特定のフィールドの開始位置*N*は、前のフィールドの開始位置と、前のフィールドとフィールドに指定した (位置指定) オフセットの長さ*N*.</span><span class="sxs-lookup"><span data-stu-id="85dcb-107">In general, the starting position of a particular field *N* is the starting position of the previous field, plus the length of the previous field, plus the (positional) offset you have specified for field *N*.</span></span>  

 <span data-ttu-id="85dcb-108">Microsoft のすべてのフィールド位置の計算[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は (BizTalk Server の以前のバージョンで必要となった) コマンドを実行することがなく、-その場で、実行、自動的にします。</span><span class="sxs-lookup"><span data-stu-id="85dcb-108">All field position calculation in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is performed automatically, on-the-fly, without any need to execute a command (as was required in previous versions of BizTalk Server).</span></span>  

## <a name="see-also"></a><span data-ttu-id="85dcb-109">参照</span><span class="sxs-lookup"><span data-stu-id="85dcb-109">See Also</span></span>  
- [<span data-ttu-id="85dcb-110">位置指定レコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="85dcb-110">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
- <span data-ttu-id="85dcb-111">**位置指定値 (フラット ファイル スキーマのノード プロパティ)** と**位置指定オフセット (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="85dcb-111">**Positional Length (Node Property of Flat File Schemas)** and **Positional Offset (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
