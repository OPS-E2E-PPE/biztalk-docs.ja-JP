---
title: "手順 2: V2.4 用の共通のスキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60b199bcd350a3341640baa05b875347c4f04bb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-create-common-schemas-for-v24"></a>手順 2: V2.4 の一般的なスキーマを作成します。
V2.4 スキーマは、頻繁に参照されるスキーマは、クエリと応答メッセージ インスタンスの検証に使用します。  
  
### <a name="to-create-the-common-schemas-for-v24"></a>V2.4 の一般的なスキーマを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。  
  
3.  **テンプレート**一覧で、 **BTAHL7V24Common プロジェクト**です。  
  
4.  **名前**フィールドに「 **Interrogative_24Schemas**です。  
  
5.  ソリューション フィールドで、選択**ソリューションに追加**、順にクリック**OK**です。  
  
     ソリューション エクスプ ローラーで、プロジェクトに 3 つのスキーマ (datatypes_24.xsd、segments_24.xsd、および tablevalues_24.xsd) が含まれていることを確認します。  
  
6.  ソリューション エクスプ ローラーで右クリック**Interrogative_24Schemas**プロジェクトをクリックして**プロパティ**です。  
  
7.  Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。  
  
8.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。  
  
9. **アセンブリ キー ファイル** ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータInterrogative チュートリアルをクリックして**key.snk**、順にクリック**開く**です。  
  
10. Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[ **OK**して変更を保存します。  
  
11. ソリューション エクスプ ローラーで右クリック**Interrogative_24Schemas**プロジェクトをクリックして**展開**です。 をクリックして**OK**ソリューションに変更を保存するように求めるダイアログ ボックスにします。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。  
  
 進みます[手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトを配置](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)です。