---
title: BAM 構成スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], scaling
- scaling, BAM
- BAM, scaling
- configuration schema [BAM]
ms.assetid: 7eeeb07f-012e-44eb-a8b5-06e374946e2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4ece27da0bdbfe43981add9d7f39aeb0ba7a89e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358602"
---
# <a name="bam-configuration-schema"></a>BAM 構成スキーマ
BAM 構成スキーマは、インフラストラクチャに関する情報を含む XML ドキュメントを定義しており、BAM マネージャー ユーティリティでは、この情報を展開に使用します。 データベースを複数のサーバーに展開して、スケーラビリティを向上させることができます。 このスケーラビリティをサポートするには、BAM 構成 XML ドキュメントに、複数のサーバー名と次のデータベースの構成設定を含める必要があります。  
  
-   BAMPrimaryImport  
  
-   BAMStarSchema  
  
-   BAMAnalysis  
  
-   BAMArchive  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM DTS パッケージ](../core/bam-dts-packages.md)  
  
## <a name="see-also"></a>参照  
 [BAM ランタイムの設定の変更](../core/changing-bam-runtime-settings.md)