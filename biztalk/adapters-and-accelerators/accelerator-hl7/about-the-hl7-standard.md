---
title: HL7 標準について |Microsoft ドキュメント
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
ms.openlocfilehash: 9185248b5b897fbc7c909786c419b07fc3fb9d61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204842"
---
# <a name="about-the-hl7-standard"></a><span data-ttu-id="f78b7-102">HL7 標準について</span><span class="sxs-lookup"><span data-stu-id="f78b7-102">About the HL7 Standard</span></span>
<span data-ttu-id="f78b7-103">正常性レベル 7 (HL7) 標準の目的は、医療環境での通信を容易にです。</span><span class="sxs-lookup"><span data-stu-id="f78b7-103">The purpose of the Health Level Seven (HL7) standard is to facilitate communication in health care environments.</span></span> <span data-ttu-id="f78b7-104">主な目的を排除またはそれ以外の場合必要なカスタム インターフェイス プログラミングおよびプログラムのメンテナンスを大幅に短縮する、医療コンピューター アプリケーション間のデータの交換標準を提供します。</span><span class="sxs-lookup"><span data-stu-id="f78b7-104">The primary goal is to provide standards for the exchange of data among health care computer applications that eliminate or substantially reduce the custom interface programming and program maintenance that may otherwise be required.</span></span> <span data-ttu-id="f78b7-105">この主な目的は、目標値のセットとして区切ることができます。</span><span class="sxs-lookup"><span data-stu-id="f78b7-105">You can delineate this primary goal as a set of goals:</span></span>  
  
-   <span data-ttu-id="f78b7-106">標準がサポートしているさまざまな技術的な環境に実装されているシステム間で交換します。</span><span class="sxs-lookup"><span data-stu-id="f78b7-106">That the standard supports exchanges among systems implemented in the widest variety of technical environments.</span></span> <span data-ttu-id="f78b7-107">その実装は、さまざまなプログラミング言語およびオペレーティング システムで実用的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f78b7-107">Its implementation should be practical in a wide variety of programming languages and operating systems.</span></span> <span data-ttu-id="f78b7-108">さまざまな通信環境では、完全な範囲内の通信もサポートする必要があります OSI 準拠、7 つのレベルのネットワーク プリミティブ point-to-point RS 232 C を含む完全な小さいの環境に「スタック」相互接続と転送フロッピー ディスクやテープなどのバッチのメディアでのデータです。</span><span class="sxs-lookup"><span data-stu-id="f78b7-108">It should also support communications in a wide variety of communications environments, ranging from a full, OSI-compliant, seven level network "stack" to less complete environments, including primitive point-to-point RS 232C interconnections and transfer of data by batch media, such as floppy disk and tape.</span></span>  
  
-   <span data-ttu-id="f78b7-109">標準がサポートしている複数のトランザクションのファイルの転送と共に 1 つのトランザクションの即時転送します。</span><span class="sxs-lookup"><span data-stu-id="f78b7-109">That the standard supports immediate transfer of single transactions along with file transfers of multiple transactions.</span></span>  
  
-   <span data-ttu-id="f78b7-110">標準は、可能な最大限の標準化、使用状況と特定のデータ要素の形式でサイトのバリエーションを一貫性のあるを実現します。</span><span class="sxs-lookup"><span data-stu-id="f78b7-110">That the standard achieves the greatest possible degree of standardization, consistent with site variations in the usage and format of certain data elements.</span></span> <span data-ttu-id="f78b7-111">標準は、必要なサイト固有の変動に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f78b7-111">The standard should accommodate necessary site-specific variations.</span></span> <span data-ttu-id="f78b7-112">これが含まれます、少なくとも、サイト固有のテーブル、コードの定義、および可能性のあるサイト固有のメッセージ セグメント (たとえば、HL7 Z セグメント)。</span><span class="sxs-lookup"><span data-stu-id="f78b7-112">This will include, at least, site-specific tables, code definitions, and possibly site-specific message segments (for example, HL7 Z segments).</span></span>  
  
-   <span data-ttu-id="f78b7-113">標準がサポートしている革新的な成長ように新しい要件が認識されます。</span><span class="sxs-lookup"><span data-stu-id="f78b7-113">That the standard must support evolutionary growth as new requirements are recognized.</span></span> <span data-ttu-id="f78b7-114">これには、既存の運用環境に拡張機能や新しいリリースを導入するプロセスのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f78b7-114">This includes support of the process of introducing extensions and new releases into existing operational environments.</span></span>  
  
-   <span data-ttu-id="f78b7-115">HL7 組織基、標準には、既存の運用プロトコルや、受理された業界標準の標準プロトコルによって発生します。</span><span class="sxs-lookup"><span data-stu-id="f78b7-115">That the HL7 organization should base the standard on experiences with existing production protocols and accepted industry-wide standard protocols.</span></span> <span data-ttu-id="f78b7-116">ただし、標準が悪影響を及ぼさないように、標準の他のユーザーに特定の会社の独自の関心に向いていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="f78b7-116">However, the standard should not favor the proprietary interests of specific companies to the detriment of other users of the standard.</span></span> <span data-ttu-id="f78b7-117">同時に、HL7 は個別の仕入先が、marketplace にもたらす一意の属性を保持するためにシークします。</span><span class="sxs-lookup"><span data-stu-id="f78b7-117">At the same time, HL7 seeks to preserve the unique attributes that an individual vendor can bring to the marketplace.</span></span>  
  
-   <span data-ttu-id="f78b7-118">利便性と関連する情報システム入院期間内に重点を置くですが、標準の長期的な目標が医療のすべての環境の形式とコンピューター アプリケーション用のプロトコルを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f78b7-118">While it is both useful and pertinent to focus on information systems within hospitals, the long-term goal of the standard should be to define formats and protocols for computer applications in all health care environments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f78b7-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f78b7-119">In This Section</span></span>  
  
-   [<span data-ttu-id="f78b7-120">HL7 のバージョン</span><span class="sxs-lookup"><span data-stu-id="f78b7-120">HL7 Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md)