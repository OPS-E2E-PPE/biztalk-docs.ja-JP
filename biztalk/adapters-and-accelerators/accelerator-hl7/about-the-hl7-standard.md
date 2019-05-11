---
title: HL7 標準の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- standards [HL7]
- HL7, standards
- Health Level Seven (HL7)
ms.assetid: 15f26ae3-d1ad-40a4-aafe-7148ef30cadb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34234723c05ac14c6e7964ce23ee1ef394760796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244450"
---
# <a name="about-the-hl7-standard"></a><span data-ttu-id="4c257-102">HL7 標準の概要</span><span class="sxs-lookup"><span data-stu-id="4c257-102">About the HL7 Standard</span></span>
<span data-ttu-id="4c257-103">正常性レベル 7 (HL7) 標準の目的は、医療の環境での通信を容易にです。</span><span class="sxs-lookup"><span data-stu-id="4c257-103">The purpose of the Health Level Seven (HL7) standard is to facilitate communication in health care environments.</span></span> <span data-ttu-id="4c257-104">主な目的は、削除するか、それ以外の場合必要ありますカスタム インターフェイス プログラミングとプログラムのメンテナンスを大幅に短縮する、医療コンピューター アプリケーション間のデータの交換標準を提供することです。</span><span class="sxs-lookup"><span data-stu-id="4c257-104">The primary goal is to provide standards for the exchange of data among health care computer applications that eliminate or substantially reduce the custom interface programming and program maintenance that may otherwise be required.</span></span> <span data-ttu-id="4c257-105">この主な目的は、目標のセットとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4c257-105">You can delineate this primary goal as a set of goals:</span></span>  
  
-   <span data-ttu-id="4c257-106">標準は、さまざまな技術的な環境で実装されたシステム間で交換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4c257-106">That the standard supports exchanges among systems implemented in the widest variety of technical environments.</span></span> <span data-ttu-id="4c257-107">その実装は、さまざまな言語およびオペレーティング システムをプログラミングで現実的でする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c257-107">Its implementation should be practical in a wide variety of programming languages and operating systems.</span></span> <span data-ttu-id="4c257-108">さまざまな通信環境では、完全な範囲での通信もサポートする必要があります OSI 準拠、7 つのレベルのネットワーク「スタック」プリミティブ point-to-point RS 232 C を含む小さい完全な環境に相互接続およびの転送フロッピー ディスクやテープなどのバッチのメディアでのデータ。</span><span class="sxs-lookup"><span data-stu-id="4c257-108">It should also support communications in a wide variety of communications environments, ranging from a full, OSI-compliant, seven level network "stack" to less complete environments, including primitive point-to-point RS 232C interconnections and transfer of data by batch media, such as floppy disk and tape.</span></span>  
  
-   <span data-ttu-id="4c257-109">標準は、複数のトランザクションのファイルの転送と共に 1 つのトランザクションの即時転送をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4c257-109">That the standard supports immediate transfer of single transactions along with file transfers of multiple transactions.</span></span>  
  
-   <span data-ttu-id="4c257-110">標準の標準化、使用状況と特定のデータ要素の形式でサイト バリエーションを一貫性のある最大の次数を実現します。</span><span class="sxs-lookup"><span data-stu-id="4c257-110">That the standard achieves the greatest possible degree of standardization, consistent with site variations in the usage and format of certain data elements.</span></span> <span data-ttu-id="4c257-111">標準は、必要なサイト固有のバリエーションに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c257-111">The standard should accommodate necessary site-specific variations.</span></span> <span data-ttu-id="4c257-112">これは、少なくとも、サイト固有テーブルなど、コードの定義、可能性があるサイト固有のメッセージのセグメント (たとえば、HL7 Z セグメント)。</span><span class="sxs-lookup"><span data-stu-id="4c257-112">This will include, at least, site-specific tables, code definitions, and possibly site-specific message segments (for example, HL7 Z segments).</span></span>  
  
-   <span data-ttu-id="4c257-113">標準は、新しい要件が認識されて革新的な成長をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c257-113">That the standard must support evolutionary growth as new requirements are recognized.</span></span> <span data-ttu-id="4c257-114">これには、既存の運用環境に拡張機能と新しいリリースを導入するプロセスのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c257-114">This includes support of the process of introducing extensions and new releases into existing operational environments.</span></span>  
  
-   <span data-ttu-id="4c257-115">ある HL7 組織基に、標準は、既存の運用プロトコルと許容される業界標準のプロトコルを使用したエクスペリエンスします。</span><span class="sxs-lookup"><span data-stu-id="4c257-115">That the HL7 organization should base the standard on experiences with existing production protocols and accepted industry-wide standard protocols.</span></span> <span data-ttu-id="4c257-116">ただし、標準では悪影響を及ぼさないように、標準の他のユーザーに特定の会社の独自の関心を優先するされません。</span><span class="sxs-lookup"><span data-stu-id="4c257-116">However, the standard should not favor the proprietary interests of specific companies to the detriment of other users of the standard.</span></span> <span data-ttu-id="4c257-117">HL7 は同時に、個々 のベンダーが、marketplace にもたらす一意の属性を保持するためにシークします。</span><span class="sxs-lookup"><span data-stu-id="4c257-117">At the same time, HL7 seeks to preserve the unique attributes that an individual vendor can bring to the marketplace.</span></span>  
  
-   <span data-ttu-id="4c257-118">有益かつ病院内の情報システムでフォーカスに関連するが、医療のすべての環境での形式とコンピューターのアプリケーション用のプロトコルを定義する標準の長期的な目標があります。</span><span class="sxs-lookup"><span data-stu-id="4c257-118">While it is both useful and pertinent to focus on information systems within hospitals, the long-term goal of the standard should be to define formats and protocols for computer applications in all health care environments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c257-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c257-119">In This Section</span></span>  
  
-   [<span data-ttu-id="4c257-120">HL7 のバージョン</span><span class="sxs-lookup"><span data-stu-id="4c257-120">HL7 Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md)