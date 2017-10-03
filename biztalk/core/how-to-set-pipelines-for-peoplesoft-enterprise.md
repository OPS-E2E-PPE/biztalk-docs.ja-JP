---
title: "PeopleSoft Enterprise のパイプラインを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting pipelines
- pipelines, setting
ms.assetid: 36914615-eac0-47b6-9e66-deeb40d21f10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69bebce2dadf0bb038b0e8c56ffa544ad02c78ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a>PeopleSoft Enterprise のパイプラインを設定する方法
Microsoft BizTalk Adapter for PeopleSoft Enterprise では、適切なパイプラインを選択する必要があります。  
  
## <a name="setting-pipelines"></a>パイプラインの設定  
  
#### <a name="to-set-pipelines"></a>パイプラインを設定するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。  
  
    2.  **型**ドロップダウン リストで、 **PeopleSoft**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
4.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)