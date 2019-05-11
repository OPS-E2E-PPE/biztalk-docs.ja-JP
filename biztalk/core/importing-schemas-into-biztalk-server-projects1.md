---
title: BizTalk Server Projects1 にスキーマのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9bcebbb138d12514bbd6c6dbac1874e81f438e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382466"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>BizTalk Server プロジェクトへのスキーマのインポート
次の情報には、BizTalk Server プロジェクトにスキーマをインポートする方法について説明します。  
  
## <a name="importing-schemas"></a>スキーマのインポート  
  
#### <a name="to-import-schemas"></a>スキーマをインポートするには  
  
1. ソリューション エクスプ ローラーでプロジェクトを右クリックして**追加**、選び**生成した項目の追加**します。  
  
2. をクリックして**アダプタの追加**、し、**オープン**します。  
  
3. アダプターを選択して<strong>、j. d.Edwards OneWorld XE</strong>します。  
  
4. ボックスの一覧で、ポートを選択します。 **[SSOSendToJD Edwards OneWorld XE**、] をクリックし、**次**。  
  
    MyJ.D します。 Edwards OneWorld XESSO 論理システムが (この論理システムは、によりで作成されましたブラウザーに表示されます。 Edwards OneWorld XE ポート)。  
  
5. 展開**myJ.D します。Edwards OneWorld XESSO**します。  
  
6. アイテムを移動 (またはドラッグするだけで) 矢印アイコンをクリックして、**送信**ウィンドウ、およびクリック**OK**。  
  
    スキーマは、SSOSchedule プロジェクトに追加されます。  
  
7. ソリューション エクスプ ローラーで、 **SSOSchedule プロジェクト**します。  
  
8. 右クリック**BizTalk orchestration.odx**、 をクリックし、**削除**します。  
  
9. ソリューション エクスプ ローラーでダブルクリック**GetList.odx**オーケストレーションを検査します。  
  
## <a name="orchestration-types---port-types"></a>オーケストレーションの種類 - ポートの種類  
  
-   **PortTypeIn/で/要求:** SSOSchedule.myJ.D します。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeOut/Out/response:** SSOSchedule.myJ.D します。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
-   **PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D します。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeInOut/InOut/応答:** SSOSchedule.myJ.D します。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="orchestration-variables---messages"></a>オーケストレーション変数 - メッセージ  
  
-   **MessageIn:** SSOSchedule.myJ.D します。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **MessageOut:** SSOSchedule.myJ.D します。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)