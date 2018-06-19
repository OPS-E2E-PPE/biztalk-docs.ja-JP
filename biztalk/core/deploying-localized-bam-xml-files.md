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
# <a name="deploying-localized-bam-xml-files"></a>ローカライズされた BAM XML ファイルの展開
Microsoft SQL Server Analysis Services では、Unicode マッピングがサポートされます。 ただし、SQL Server Analysis Services と Visual Basic の Unicode マッピングには、文字が正しく表示されないという既知の問題が存在します。 具体的には、ANSI から Unicode への変換を行うときに地域別設定を適切なローカライズ言語に設定していないと、不適切なロケール情報を使用して変換が行われるので、文字が正しく表示されません。  
  
 BAM 定義 XML ファイルを適切に展開するには、ローカライズされた文字が含まれている BAM 定義 XML ファイルを実際に展開する前に、システム ロケールを適切なロケールに切り替える必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)