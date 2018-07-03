---
title: フラット ファイル メッセージのスキーマを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f2747b-7f26-4fb2-a855-523e093f3813
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4459012155ca95166b6345ddad4390e78fce60c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984467"
---
# <a name="create-schemas-for-flat-file-messages"></a><span data-ttu-id="e9c74-102">フラット ファイル メッセージ用スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c74-102">Create Schemas for Flat File Messages</span></span>

## <a name="overview"></a><span data-ttu-id="e9c74-103">概要</span><span class="sxs-lookup"><span data-stu-id="e9c74-103">Overview</span></span>
<span data-ttu-id="e9c74-104">」の説明に従って XML メッセージ スキーマの作成後に[XML メッセージ用スキーマの作成](../core/how-to-create-schemas-for-xml-messages.md)を使用して、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**ノードを有効にする、フラット ファイル拡張機能。</span><span class="sxs-lookup"><span data-stu-id="e9c74-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), use the **Schema Editor Extensions** property of the **Schema** node to enable the flat file extension.</span></span> <span data-ttu-id="e9c74-105">フラット ファイル拡張機能を有効にすると、スキーマ内の各種ノードに、多数のプロパティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e9c74-105">Enabling the flat file extension adds a considerable number of properties to many of the node types within a schema.</span></span> <span data-ttu-id="e9c74-106">一般に、これらのプロパティは、フラット ファイル形式のビジネス ドキュメントと、XML 形式のビジネス ドキュメント間の変換方法を制御する目的で使用され、対応するプロパティ値は XSD (XML Schema Definition) 言語の注釈としてスキーマ ファイル内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="e9c74-106">These properties are generally used to control how a flat file business document is translated to and from its equivalent XML business document, and their values are stored as XML Schema definition language (XSD ) annotations within the schema file.</span></span> <span data-ttu-id="e9c74-107">これらのプロパティを適切に使用するためには、多少の学習が必要になります。各プロパティがフラット ファイル形式のどのような側面を定義しているのかを、十分に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9c74-107">Using these properties properly takes some practice and a thorough understanding of which aspects of the flat file format they each govern.</span></span> 

<span data-ttu-id="e9c74-108">概念と、フラット ファイル プロパティに関する参照情報を参照してください[に関する考慮事項とフラット ファイル メッセージ スキーマの作成](../core/considerations-when-creating-flat-file-message-schemas.md)と**フラット ファイル スキーマの補足のノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="e9c74-108">For conceptual and reference information about the flat file properties, see [Considerations When Creating Flat File Message Schemas](../core/considerations-when-creating-flat-file-message-schemas.md) and **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  

## <a name="see-also"></a><span data-ttu-id="e9c74-109">参照</span><span class="sxs-lookup"><span data-stu-id="e9c74-109">See Also</span></span>  
- [<span data-ttu-id="e9c74-110">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="e9c74-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
- <span data-ttu-id="e9c74-111">詳細については、これらのプロパティ [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c74-111">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
