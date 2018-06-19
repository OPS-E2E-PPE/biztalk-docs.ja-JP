---
title: ローカライズされた BAM XML ファイルを展開する |Microsoft ドキュメント
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
ms.openlocfilehash: 3452f13569ca6a0c0bb5843995c07a15b30f4da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239314"
---
# <a name="deploying-localized-bam-xml-files"></a><span data-ttu-id="3fc67-102">ローカライズされた BAM XML ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="3fc67-102">Deploying Localized BAM XML Files</span></span>
<span data-ttu-id="3fc67-103">Microsoft SQL Server Analysis Services では、Unicode マッピングがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3fc67-103">Microsoft SQL Server Analysis Services supports Unicode mapping.</span></span> <span data-ttu-id="3fc67-104">ただし、SQL Server Analysis Services と Visual Basic の Unicode マッピングには、文字が正しく表示されないという既知の問題が存在します。</span><span class="sxs-lookup"><span data-stu-id="3fc67-104">However, there are known character corruption issues with SQL Server Analysis Services and Visual Basic Unicode mapping.</span></span> <span data-ttu-id="3fc67-105">具体的には、ANSI から Unicode への変換を行うときに地域別設定を適切なローカライズ言語に設定していないと、不適切なロケール情報を使用して変換が行われるので、文字が正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="3fc67-105">Specifically, if the regional settings are not set to the correct localized language when the conversion from ANSI to Unicode occurs, the conversion is performed using the wrong locale information and character corruption occurs.</span></span>  
  
 <span data-ttu-id="3fc67-106">BAM 定義 XML ファイルを適切に展開するには、ローカライズされた文字が含まれている BAM 定義 XML ファイルを実際に展開する前に、システム ロケールを適切なロケールに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc67-106">To deploy the BAM definition XML file successfully, you must switch your system locale to the correct locale before you can actually deploy a BAM definition XML file that contains localized characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc67-107">参照</span><span class="sxs-lookup"><span data-stu-id="3fc67-107">See Also</span></span>  
 <span data-ttu-id="3fc67-108">[BAM の管理](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="3fc67-108">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="3fc67-109">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3fc67-109">BAM Management Utility</span></span>](../core/bam-management-utility.md)