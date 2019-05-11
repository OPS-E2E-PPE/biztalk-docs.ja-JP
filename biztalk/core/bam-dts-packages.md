---
title: BAM DTS パッケージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30cbcb583f1e175f5d65565c2108361ec9121721
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528886"
---
# <a name="bam-dts-packages"></a>BAM DTS パッケージ
管理者は、次の BAM DTS パッケージのパラメーターを更新できます。  
  
- **CubeUpdate**データ変換サービス (DTS) パッケージは、スター スキーマ データベースと同じサーバー上にある常にします。  
  
- **DataMaintenance** DTS パッケージは、プライマリ インポート データベースと同じサーバー上にある常にします。  
  
  DTS パッケージは、BAMConfiguration.xml ファイルで、次のパラメーターを使用します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ConnectionTimeOut|DTS 接続のタイムアウト値 (秒) では、整数です。 ConnectionTimeOut パラメーターを省略した場合、構成ファイルには、60 秒で、既定値が使用されます。|  
|暗号化|既定では、DTS パッケージはデータは暗号化データの変換中に (暗号化値は 0)。 変換中にデータを暗号化するには 1 には、暗号化を設定します。|  
|OwnerPassword|DTS パッケージの所有者のパスワード。 DTS パッケージの所有者が開き、DTS パッケージを変更できます。 DTS パッケージの所有者の詳細については、SQL Server オンライン ブックを参照してください。|  
|UserPassword|Dts パッケージ ユーザーのパスワード。 DTS パッケージのユーザーには、DTS パッケージを実行できます。 DTS パッケージのユーザーについては、SQL Server オンライン ブックを参照してください。|  
  
 DTS パッケージは、BAMConfiguration.xml ファイルで、次の名前付け規則を使用します。  
  
- **CubeUpdate** DTS パッケージ  
  
   **bam_an _\<**  ***CubeName* \>** CubeName はキューブの名前です。 BAM ブックでは、ビュー名からキューブ名を生成します。 BAM 構成 XML ドキュメントでキューブ名を変更する場合、新しいキューブ名は、DTS パッケージ名に使用されます。  
  
- **DataMaintenance** DTS パッケージ  
  
   **bam_dm _\<**  ***ActivityName* \>** ActivityName はアクティビティの名前です。  
  
  スケジュール済みの集計を集計する CubeUpdate DTS パッケージを実行するとします。 次のセクションでは、リアルタイムのデータ集計の時間枠を指定できます。  
  
## <a name="see-also"></a>参照  
 [BAM 構成スキーマ](../core/bam-configuration-schema.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM の管理](../core/managing-bam.md)