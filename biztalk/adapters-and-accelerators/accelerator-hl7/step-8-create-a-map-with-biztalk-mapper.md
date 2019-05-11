---
title: 手順 8:BizTalk マッパーでマップの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 973dde183178be48feeea2613c0cf6964c9f3efa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287866"
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a>手順 8:BizTalk マッパーでマップを作成します。
この手順では、BizTalk マッパーを使用してマップを作成します。 データ (フィールド) に関連付けるリンクを作成するのにドキュメントが拒否された要求のデータに補充要求ドキュメントでこのマップを使用するとします。  
  
### <a name="to-create-a-map"></a>マップを作成するには  
  
1. ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2. **新しい項目の追加** ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**マップ ファイル**します。  
  
3. **名前**フィールドに「 **DoorbellMap** 、マップの名前をクリックして**追加**を BizTalk マッパーを開始します。  
  
4. **送信元スキーマ**ウィンドウ (左側) をクリックします**ソース スキーマを開く**します。  
  
5. BizTalk 型の選択 ダイアログ ボックスで、 **BTAHL7 プロジェクト**、展開**スキーマ**、 をクリックして**BTAHL7_Project.Doorbell**、順にクリックします**OK**.  
  
6. **送信先スキーマ**ウィンドウ (右側) をクリックします**送信先スキーマを開く**します。  
  
7. BizTalk 型の選択で [ **BTAHL7 プロジェクト**、展開**スキーマ**、] をクリックして**BTAHL7Schemas.ADT_A04_22_GLO_DEF**、順にクリックします**OK**.  
  
8. **送信先スキーマ**ウィンドウ (右側) 展開**ADT_A04_22_GLO_DEF**、展開**PID_PatientIdentification**、展開と**PID.5_PatientName**.  
  
9. **送信元スキーマ**ウィンドウ (左側)、展開**DoorbellRoot**します。 ドラッグ、 **LastName**フィールドを**PN_0_FamilyName**フィールドに、**送信先スキーマ**ウィンドウ。  
  
10. **送信元スキーマ**ウィンドウで、ドラッグ、 **FirstName**フィールドを**PN_1_GivenName**フィールドに、**送信先スキーマ**ウィンドウ。  
  
11. **送信元スキーマ**ウィンドウで、ドラッグ、 **MiddleName**フィールドを**PN_2_MiddleInitialOrName**フィールドに、**送信先スキーマ**ウィンドウ.  
  
12. **送信先スキーマ**ウィンドウで、展開**PID_3_PatientIdInternalId**します。  
  
13. **送信元スキーマ**ウィンドウで、ドラッグ、 **SSN**フィールドを**CM_PAT_ID_0_PatientID**で、**送信先スキーマ**ウィンドウ。  
  
14. **ファイル** メニューのをクリックして**すべて保存**します。  
  
    一般的なメッセージの強化のシナリオで、患者の情報が見つからない場合は、オーケストレーションで患者レコード データベースへの呼び出しを行うして、不足している情報を追加し、する追加の情報を使用してマッピングを完了します。 たとえば、XML ドアベル トリガー イベントの受信メッセージが提供していないために、患者レコードのデータベースから患者の自宅の住所を取得することが。  
  
    続行する[手順 9。検証し、マップのプロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)