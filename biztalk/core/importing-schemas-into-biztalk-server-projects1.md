---
title: "BizTalk Server Projects1 へのスキーマのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0e67ef4e47b62e0381d882739b2fdc012ba621
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>BizTalk Server プロジェクトへのスキーマのインポート
ここでは、BizTalk Server プロジェクトにスキーマをインポートする手順について説明します。  
  
## <a name="importing-schemas"></a>スキーマのインポート  
  
#### <a name="to-import-schemas"></a>スキーマをインポートするには  
  
1.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**を選択して**生成した項目の追加**です。  
  
2.  をクリックして**アダプタの追加**、し、**開く**です。  
  
3.  アダプターを選択して**、j. d.Edwards OneWorld XE**です。  
  
4.  ドロップダウン リストで、ポートを選択**SSOSendToJD Edwards OneWorld XE**、クリックして**次**です。  
  
     MyJ.D です。 Edwards OneWorld XESSO 論理システムが (この論理システムは、SSOSendToJ.D で作成されましたブラウザーに表示されます。 Edwards OneWorld XE ポート)。  
  
5.  展開**myJ.D です。Edwards OneWorld XESSO**です。  
  
6.  項目へ移動します (またはドラッグ) にある矢印アイコンをクリックして、**送信**ウィンドウ、およびクリック**[ok]**です。  
  
     SSOSchedule プロジェクトにスキーマが追加されます。  
  
7.  ソリューション エクスプ ローラーで、 **SSOSchedule プロジェクト**です。  
  
8.  右クリック**BizTalk orchestration.odx**、クリックして**削除**です。  
  
9. ソリューション エクスプ ローラーで、 **GetList.odx**をオーケストレーションを検査します。  
  
## <a name="orchestration-types---port-types"></a>オーケストレーションの種類 - ポートの種類  
  
-   **PortTypeIn/で/要求:** SSOSchedule.myJ.D です。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeOut/アウト/応答:** SSOSchedule.myJ.D です。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
-   **PortTypeInOut/InOut/要求:** SSOSchedule.myJ.D です。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeInOut/InOut/応答:** SSOSchedule.myJ.D です。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="orchestration-variables---messages"></a>オーケストレーション変数 - メッセージ  
  
-   **MessageIn:** SSOSchedule.myJ.D です。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **MessageOut:** SSOSchedule.myJ.D です。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="see-also"></a>参照  
 [シングル サインオンを使用します。](../core/using-single-sign-on3.md)