---
title: "JD Edwards EnterpriseOne アダプターのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b3e68fa-b81d-4767-ab62-3200ce89d81c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d46fd3375f49f9fabd6ce8028cc226bce5885db
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne のトラブルシューティング

## <a name="overview"></a>概要
ここでは、BizTalk Adapter for JD Edwards EnterpriseOne で発生する可能性がある一般的な問題およびエラー メッセージについて説明し、考えられる修正方法を示します。 さらに、Windows イベント トレーシングの使用について説明します。  
  
 以下のデバッグ/トレース ツールを使用して、アダプターのトラブルシューティングを行うことができます。  
  
-   BizTalk Server のネイティブなデバッグ機能 (たとえば、ポートの [追跡の種類] やオーケストレーション デバッガー)。  
  
-   イベント ログに送信されるエラー メッセージ。  
  
-   BTAJDEEnterpriseOneTrace.cmd および .etl ファイル変換ツール (tracerpt.exe や tracedmp.exe など) による、送信元、受信元、および管理メッセージのキャプチャ。  
  
## <a name="next-steps"></a>次の手順
  
-   [エラー メッセージ](../core/error-messages1.md)  
  
-   [Windows イベント トレーシングの使用](../core/using-event-tracing-for-windows4.md)  
  
-   [アダプターのトラブルシューティング](../core/troubleshooting-the-adapter1.md)