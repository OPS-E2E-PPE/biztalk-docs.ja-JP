---
title: 区切られたレコードの処理をタグ付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50a3daad9bb77ba4a9cbc264f018e29601edfff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972467"
---
# <a name="tag-handling-in-delimited-records"></a><span data-ttu-id="724b0-102">タグで区切られたレコードの処理</span><span class="sxs-lookup"><span data-stu-id="724b0-102">Tag Handling in Delimited Records</span></span>

## <a name="overview"></a><span data-ttu-id="724b0-103">概要</span><span class="sxs-lookup"><span data-stu-id="724b0-103">Overview</span></span>
<span data-ttu-id="724b0-104">区切られたレコードには、レコードの種類を明確に区別するための、タグという文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="724b0-104">Delimited records can include a well-known sequence of characters, known as a tag, which can be used to disambiguate one type of record from another.</span></span> <span data-ttu-id="724b0-105">これにより、適切なを正しく識別するためにフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="724b0-105">This will allow the flat file disassembler to properly identify the appropriate **Record** node in the schema that contains the information required to correctly parse the flat file record.</span></span>  

 <span data-ttu-id="724b0-106">使用することができます、**タグ識別子**区切られたレコードでタグを指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="724b0-106">You can use the **Tag Identifier** property to specify the tag within a delimited record.</span></span> <span data-ttu-id="724b0-107">位置指定レコードのタグとは異なり、区切られたレコードのタグは、区切られたレコードの先頭に設定されている必要があります。また、等価な XML 形式に変換される際、タグはデータから自動的に除外されます。</span><span class="sxs-lookup"><span data-stu-id="724b0-107">Unlike tags in positional records, tags in delimited records must occur at the beginning of the delimited record and are automatically never included in the data when the record is translated to its equivalent XML format.</span></span>  

## <a name="see-also"></a><span data-ttu-id="724b0-108">参照</span><span class="sxs-lookup"><span data-stu-id="724b0-108">See Also</span></span>  
- [<span data-ttu-id="724b0-109">区切り記号付きレコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="724b0-109">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="724b0-110">**タグ識別子 (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="724b0-110">**Tag Identifier (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
