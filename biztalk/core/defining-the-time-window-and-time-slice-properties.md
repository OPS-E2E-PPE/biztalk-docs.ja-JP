---
title: "時間枠とタイム スライスのプロパティを定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d846b03866196e0a31facbbff68db50ec6a00a5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-the-time-window-and-time-slice-properties"></a>TimeWindow プロパティと TimeSlice プロパティの定義
管理者は、BAMConfiguration.xml ファイルの TimeWindow プロパティと TimeSlice プロパティを使用して、BAM プライマリ インポート データベースのリアルタイム集計のテーブルに格納されるデータの有効期間を定義することができます。  
  
> [!NOTE]
>  BAM 構成ファイルに加えた変更を反映するには、管理者が、現在展開している BAM 構成の展開を解除し、更新した BAMConfiguration.xml を展開する必要があります。  
  
 BAM 定義を展開解除については、次を参照してください。 [BAM 定義を削除する方法](../core/how-to-remove-bam-definitions.md)です。 BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)です。  
  
 BAM インフラストラクチャの展開を解除せずに TimeWindow プロパティと TimeSlice プロパティの値を変更する必要がある場合は、BAM プライマリ インポート データベースの BAM_Metadata_Activities テーブルの列を編集することができます。  
  
## <a name="timeslice"></a>TimeSlice  
 TimeSlice プロパティは、完了した BAM インスタンス データのグループ化に使用します。 このプロパティでは、データが BAM プライマリ インポート データベースに書き込まれた時刻を BAM インスタンス データのグループ化に使用しています。  
  
 インスタンス A が完了し、1/1/2000 で BAM プライマリ インポート データベースに永続化など、午前 1時 02分 インスタンス B が完了し、1/1/2000 で BAM プライマリ インポート データベースに永続化午前 1時 04分 TimeSlice プロパティの値を 5 分に設定した場合、インスタンス A と B のインスタンスは一緒に分類されます。  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a>BAM 構成ファイルで TimeSlice プロパティの値を変更するには  
  
-   BAM 構成ファイルで、次の行の値を変更します。  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a>BAM_Metadata_Activities テーブルで timeslice プロパティの値を変更するには  
  
-   BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある RTATimeSlice プロパティの値を変更します。 1 つ以上のアクティビティを対象としたリアルタイム集計 (TRA) を複数展開している場合は、RTA ごとに別の時間帯を指定できます。  
  
    > [!NOTE]
    >  RTAWindow の値は整数値で指定する必要があり、時間の単位は常に分になります。  
  
## <a name="timewindow"></a>TimeWindow  
 CubeUpdate DTS パッケージを実行すると、データが BAM プライマリ インポート データベースから BAM キューブに移動されます。 パッケージは、グループ内のすべてのデータが RTAWindow プロパティで指定した期間を経過したときに、リアルタイム集計のデータを、グループ化された BAM データ インスタンスとして移動します。  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a>BAM 構成ファイルで TimeWindow プロパティの値を変更するには  
  
-   BAM 構成ファイルで、次の行の値を変更します。  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a>BAM_Metadata_Activities テーブルで TimeWindow プロパティの値を変更するには  
  
-   BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある RTAWindow プロパティの値を変更します。 1 つ以上のアクティビティを対象としたリアルタイム集計 (TRA) を複数展開している場合は、RTA ごとに別の時間帯を指定できます。  
  
    > [!NOTE]
    >  RTAWindow の値は整数値で指定する必要があり、時間の単位は常に分になります。  
  
## <a name="see-also"></a>参照  
 [BAM 構成スキーマ](../core/bam-configuration-schema.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)