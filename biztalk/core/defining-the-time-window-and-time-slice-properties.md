---
title: Timewindow プロパティと Timeslice プロパティの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- managing [BAM], real-time data
- Primary Import database [BAM], time properties
- aggregations [BAM], managing
- Primary Import database [BAM], real-time data
- BAMConfiguration.xml file
- aggregations [BAM], real-time data
ms.assetid: 7f07b179-da10-4702-baf7-69516c8f16a6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 902d50596185de13792e5d03b0d7e0dbd4238f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352355"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a>TimeWindow プロパティと TimeSlice プロパティの定義
管理者を使用して、timewindow プロパティと TimeSlice プロパティ BAMConfiguration.xml ファイルで、BAM プライマリ インポート データベースのリアルタイム集計のテーブルにデータの有効期間を定義します。  
  
> [!NOTE]
>  BAM 構成ファイルの変更を適用するには、は、管理者は現在 BAM 構成では、展開解除し、更新した BAMConfiguration.xml を展開する必要があります。  
  
 BAM 定義を展開解除については、次を参照してください。 [BAM 定義を削除する方法](../core/how-to-remove-bam-definitions.md)します。 BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)します。  
  
 BAM インフラストラクチャの展開を解除せずに timewindow プロパティと timeslice プロパティの値を変更する場合は、BAM プライマリ インポート データベースの BAM_Metadata_Activities テーブルの列を変更することができます。  
  
## <a name="timeslice"></a>タイム スライス  
 BAM インスタンス データのグループ化の完了します。 TimeSlice プロパティを使用するとします。 TimeSlice プロパティは、データが BAM インスタンス データのグループに BAM プライマリ インポート データベースに書き込まれた時刻を使用します。  
  
 インスタンス A が完了し、2000/1/1 に、BAM プライマリ インポート データベースに永続化など、午前 1時 02分 インスタンス B が完了し、2000/1/1 に、BAM プライマリ インポート データベースに永続化の午前 1時 04分 TimeSlice プロパティの値を 5 分に設定する場合は、インスタンス A と B のインスタンス化されます。  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a>BAM 構成ファイルで timeslice プロパティの値を変更するには  
  
-   BAM 構成ファイルの行の値を変更します。  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a>BAM_Metadata_Activities テーブルで timeslice プロパティの値を変更するには  
  
-   BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある rtatimeslice プロパティの値を変更します。 1 つまたは複数のアクティビティに複数のリアルタイム集計 (RTA) をデプロイする場合は、rta ごとに、異なる時間枠を指定するオプションがあります。  
  
    > [!NOTE]
    >  Rtawindow プロパティの値は整数である必要があります、時間単位は分では常にします。  
  
## <a name="timewindow"></a>Timewindow プロパティ  
 CubeUpdate DTS パッケージを実行すると、パッケージでは、BAM プライマリ インポート データベースからデータを BAM キューブに移動します。 パッケージは、BAM データのグループ化されたインスタンスすべて、グループ内のデータが Rtawindow プロパティで指定された有効期間より古い、リアルタイム集計データを移動します。  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a>BAM 構成ファイルで timewindow プロパティの値を変更するには  
  
-   BAM 構成ファイルの行の値を変更します。  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a>BAM_Metadata_Activities テーブルで timewindow プロパティの値を変更するには  
  
-   BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある rtawindow プロパティの値を変更します。 1 つまたは複数のアクティビティに複数のリアルタイム集計 (RTA) をデプロイする場合は、rta ごとに、異なる時間枠を指定するオプションがあります。  
  
    > [!NOTE]
    >  Rtawindow プロパティの値は整数である必要があります、時間単位は分では常にします。  
  
## <a name="see-also"></a>参照  
 [BAM 構成スキーマ](../core/bam-configuration-schema.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)