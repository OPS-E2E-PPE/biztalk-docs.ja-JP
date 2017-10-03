---
title: "手順 8: BizTalk マッパーでマップの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48e2578211d65ade2a50916e909c87a6fd84bf44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a>手順 8: BizTalk マッパーでマップを作成します。
このステップでは、BizTalk マッパーを使用してマップを作成します。 データ (フィールド) に関連付けているリンクを作成するのにドキュメントを拒否された要求内のデータに補充要求ドキュメントでこのマップを使用するとします。  
  
### <a name="to-create-a-map"></a>マップを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
2.  **新しい項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**マップ ファイル**です。  
  
3.  **名前**フィールドに「 **DoorbellMap** 、マップの名前を指定し [] をクリックしてする**追加**を BizTalk マッパーを起動します。  
  
4.  **送信元スキーマ**ウィンドウ (左側) をクリックします**ソース スキーマを開く**です。  
  
5.  BizTalk 型の選択 ダイアログ ボックスで、展開**BTAHL7 プロジェクト**、展開**スキーマ**、 をクリックして**BTAHL7_Project.Doorbell**、順にクリック**OK**.  
  
6.  **送信先スキーマ**ウィンドウ (右側) をクリックして**送信先スキーマを開く**です。  
  
7.  BizTalk 型の選択で、展開**BTAHL7 プロジェクト**、展開**スキーマ**、 をクリックして**BTAHL7Schemas.ADT_A04_22_GLO_DEF**、順にクリック**OK**.  
  
8.  **送信先スキーマ**ウィンドウ (右側) を展開**ADT_A04_22_GLO_DEF**、展開**PID_PatientIdentification**、展開と**PID.5_PatientName**.  
  
9. **送信元スキーマ**ウィンドウ (左側)、展開**DoorbellRoot**です。 ドラッグ、 **LastName**フィールドを**PN_0_FamilyName**フィールドで、**送信先スキーマ**ウィンドウです。  
  
10. **送信元スキーマ** ウィンドウで、ドラッグ、 **FirstName**フィールドを**PN_1_GivenName**フィールドで、**送信先スキーマ**ウィンドウです。  
  
11. **送信元スキーマ** ウィンドウで、ドラッグ、 **MiddleName**フィールドを**PN_2_MiddleInitialOrName**フィールドで、**送信先スキーマ**ペイン.  
  
12. **送信先スキーマ** ウィンドウで、展開**PID_3_PatientIdInternalId**です。  
  
13. **送信元スキーマ** ウィンドウで、ドラッグ、 **SSN**フィールドを**CM_PAT_ID_0_PatientID**で、**送信先スキーマ**ウィンドウです。  
  
14. **ファイル** メニューのをクリックして**すべて保存**です。  
  
 シナリオでは、一般的なメッセージの強化、患者の情報が見つからなかった場合は、オーケストレーションで、患者のレコードのデータベースへの呼び出しを行うして不足している情報を追加し、する追加の情報を使用して、マッピングを完了します。 たとえば、XML ドアベル トリガー イベントの受信メッセージでは提供しませんでしたので患者のレコードのデータベースから患者の自宅の住所を取得することができます。  
  
 進みます[手順 9: 検証し、マップのプロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)