---
title: BAM DTS パッケージ |Microsoft ドキュメント
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
ms.openlocfilehash: a71431ee800c80c6972747f09b0e2420f961e33e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965064"
---
# <a name="bam-dts-packages"></a>BAM DTS パッケージ
管理者は、次の BAM DTS パッケージのパラメーターを更新できます。  
  
-   **CubeUpdate**データ変換サービス (DTS) パッケージは、スター スキーマ データベースと同じサーバーで常にあります。  
  
-   **DataMaintenance** DTS パッケージは、プライマリ インポート データベースと同じサーバーで常にあります。  
  
 DTS パッケージでは、BAMConfiguration.xml ファイルで次のパラメーターを使用します。  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ConnectionTimeOut|DTS 接続のタイムアウト値 (秒単位) を整数で指定します。 ConnectionTimeOut パラメーターを指定しないと、構成ファイルでは既定値の 60 秒が使用されます。|  
|暗号化|DTS パッケージによるデータの変換中、既定ではデータが暗号化されません (Encryption の値は 0 です)。 変換中にデータを暗号化するには Encryption の値を 1 に設定します。|  
|OwnerPassword|DTS パッケージ所有者のパスワードを指定します。 DTS パッケージの所有者は、DTS パッケージを開いて変更できます。 DTS パッケージの所有者の詳細については、SQL Server Books Online を参照してください。|  
|UserPassword|DTS パッケージ ユーザーのパスワードを指定します。 DTS パッケージのユーザーは、DTS パッケージを実行できます。 DTS パッケージのユーザーの詳細については、SQL Server Books Online を参照してください。|  
  
 DTS パッケージは、BAMConfiguration.xml ファイルで次の名前付け規則を使用します。  
  
-   **CubeUpdate** DTS パッケージ  
  
     **bam_an _\<**   ***CubeName* \>** 、キューブ名は、キューブの名前を指定します。 BAM ブックでは、ビュー名からキューブ名が生成されます。 BAM 構成 XML ドキュメントでキューブ名を変更した場合、新しいキューブ名が DTS パッケージ名に使用されます。  
  
-   **DataMaintenance** DTS パッケージ  
  
     **bam_dm _\<**   ***ActivityName* \>** ここで、アクティビティ名は、アクティビティの名前。  
  
 スケジュール済みの集計を集計するには、CubeUpdate DTS パッケージを実行します。 次のセクションでは、リアルタイムのデータ集計の時間帯を指定できます。  
  
## <a name="see-also"></a>参照  
 [BAM 構成スキーマ](../core/bam-configuration-schema.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM の管理](../core/managing-bam.md)