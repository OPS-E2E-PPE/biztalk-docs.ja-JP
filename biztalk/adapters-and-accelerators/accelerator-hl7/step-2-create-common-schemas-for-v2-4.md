---
title: 手順 2:V2.4 の一般的なスキーマを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5149ba2e39f36b85f03af8f3bfb81656a5647b64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288655"
---
# <a name="step-2-create-common-schemas-for-v24"></a>手順 2:V2.4 の一般的なスキーマを作成します。
V2.4 スキーマは、頻繁に参照されるスキーマは、クエリと応答メッセージ インスタンスの検証に使用します。  
  
### <a name="to-create-the-common-schemas-for-v24"></a>V2.4 の一般的なスキーマを作成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
2. 新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。  
  
3. **テンプレート**一覧で、 **BTAHL7V24Common プロジェクト**します。  
  
4. **名前**フィールドに「 **Interrogative_24Schemas**します。  
  
5. ソリューションのフィールドで、選択**ソリューションに追加**、順にクリックします**OK**。  
  
    ソリューション エクスプ ローラーでは、(datatypes_24.xsd、segments_24.xsd、および tablevalues_24.xsd) の 3 つのスキーマをプロジェクトに含まれることに注意してください。  
  
6. ソリューション エクスプ ローラーで右クリックして**Interrogative_24Schemas**プロジェクトをクリックして**プロパティ**します。  
  
7. Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。  
  
8. 右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。  
  
9. **アセンブリ キー ファイル** ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータInterrogative チュートリアル, をクリックして**key.snk**、 をクリックし、**オープン**します。  
  
10. Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[ **OK**変更を保存します。  
  
11. ソリューション エクスプ ローラーで右クリックして**Interrogative_24Schemas**プロジェクトをクリックして**デプロイ**します。 をクリックして**OK**をソリューションに変更を保存することを確認するダイアログ ボックスにします。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。  
  
    続行する[手順 3。作成し、トリガー イベント (メッセージ) プロジェクトを配置](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)します。