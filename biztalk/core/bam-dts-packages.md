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
ms.openlocfilehash: 1e49741a0fce6fd69e4e2ba5d8bb8dbd1956a0e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015851"
---
# <a name="bam-dts-packages"></a>BAM DTS パッケージ
管理者は、次の BAM DTS パッケージのパラメーターを更新できます。  
  
- **CubeUpdate**データ変換サービス (DTS) パッケージは、スター スキーマ データベースと同じサーバー上にある常にします。  
  
- **DataMaintenance** DTS パッケージは、プライマリ インポート データベースと同じサーバー上にある常にします。  
  
  DTS パッケージでは、BAMConfiguration.xml ファイルで次のパラメーターを使用します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ConnectionTimeOut|DTS 接続のタイムアウト値 (秒単位) を整数で指定します。 ConnectionTimeOut パラメーターを指定しないと、構成ファイルでは既定値の 60 秒が使用されます。|  
|暗号化|DTS パッケージによるデータの変換中、既定ではデータが暗号化されません (Encryption の値は 0 です)。 変換中にデータを暗号化するには Encryption の値を 1 に設定します。|  
|OwnerPassword|DTS パッケージ所有者のパスワードを指定します。 DTS パッケージの所有者は、DTS パッケージを開いて変更できます。 DTS パッケージの所有者の詳細については、SQL Server Books Online を参照してください。|  
|UserPassword|DTS パッケージ ユーザーのパスワードを指定します。 DTS パッケージのユーザーは、DTS パッケージを実行できます。 DTS パッケージのユーザーの詳細については、SQL Server Books Online を参照してください。|  
  
 DTS パッケージは、BAMConfiguration.xml ファイルで次の名前付け規則を使用します。  
  
- **CubeUpdate** DTS パッケージ  
  
   **bam_an _\<**  ***CubeName* \>** CubeName はキューブの名前です。 BAM ブックでは、ビュー名からキューブ名が生成されます。 BAM 構成 XML ドキュメントでキューブ名を変更した場合、新しいキューブ名が DTS パッケージ名に使用されます。  
  
- **DataMaintenance** DTS パッケージ  
  
   **bam_dm _\<**  ***ActivityName* \>** ActivityName はアクティビティの名前です。  
  
  スケジュール済みの集計を集計するには、CubeUpdate DTS パッケージを実行します。 次のセクションでは、リアルタイムのデータ集計の時間帯を指定できます。  
  
## <a name="see-also"></a>参照  
 [BAM 構成スキーマ](../core/bam-configuration-schema.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM の管理](../core/managing-bam.md)