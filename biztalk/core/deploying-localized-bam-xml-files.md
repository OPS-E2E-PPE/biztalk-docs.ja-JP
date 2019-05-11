---
title: ローカライズされた BAM XML ファイルを展開する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, unicode mapping
- unicode mapping [BAM]
ms.assetid: 8e7e3431-cd20-45db-b7f2-0df23e9df42b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36eafa1c29da4b470710f2957d501bc9b91ccd98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352066"
---
# <a name="deploying-localized-bam-xml-files"></a><span data-ttu-id="97790-102">ローカライズされた BAM XML ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="97790-102">Deploying Localized BAM XML Files</span></span>
<span data-ttu-id="97790-103">Microsoft SQL Server Analysis Services では、Unicode マッピングがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="97790-103">Microsoft SQL Server Analysis Services supports Unicode mapping.</span></span> <span data-ttu-id="97790-104">ただし、マッピングでは SQL Server Analysis Services と Visual Basic の Unicode 文字の破損の問題が既知です。</span><span class="sxs-lookup"><span data-stu-id="97790-104">However, there are known character corruption issues with SQL Server Analysis Services and Visual Basic Unicode mapping.</span></span> <span data-ttu-id="97790-105">具体的には、地域の設定が適切に設定されていない場合は言語をローカライズ ANSI から Unicode への変換が発生した、間違ったロケール情報を使用して、変換が実行され、文字の破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="97790-105">Specifically, if the regional settings are not set to the correct localized language when the conversion from ANSI to Unicode occurs, the conversion is performed using the wrong locale information and character corruption occurs.</span></span>  
  
 <span data-ttu-id="97790-106">ローカライズされた文字を含む BAM 定義 XML ファイルを実際に展開する前に、BAM 定義 XML ファイルを正常にデプロイするには、システム ロケールに適切なロケールに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="97790-106">To deploy the BAM definition XML file successfully, you must switch your system locale to the correct locale before you can actually deploy a BAM definition XML file that contains localized characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97790-107">参照</span><span class="sxs-lookup"><span data-stu-id="97790-107">See Also</span></span>  
 <span data-ttu-id="97790-108">[BAM の管理](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="97790-108">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="97790-109">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="97790-109">BAM Management Utility</span></span>](../core/bam-management-utility.md)