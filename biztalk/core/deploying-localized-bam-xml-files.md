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
# <a name="deploying-localized-bam-xml-files"></a>ローカライズされた BAM XML ファイルの展開
Microsoft SQL Server Analysis Services では、Unicode マッピングがサポートされます。 ただし、マッピングでは SQL Server Analysis Services と Visual Basic の Unicode 文字の破損の問題が既知です。 具体的には、地域の設定が適切に設定されていない場合は言語をローカライズ ANSI から Unicode への変換が発生した、間違ったロケール情報を使用して、変換が実行され、文字の破損が発生します。  
  
 ローカライズされた文字を含む BAM 定義 XML ファイルを実際に展開する前に、BAM 定義 XML ファイルを正常にデプロイするには、システム ロケールに適切なロケールに切り替える必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)