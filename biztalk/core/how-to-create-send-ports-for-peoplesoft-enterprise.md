---
title: "PeopleSoft Enterprise の送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 374261ce-2cb5-4193-a0a2-658f989b2c60
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b6b5caa44976aec7a4afb8e0eccf5b1f8904111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a>PeopleSoft Enterprise の送信ポートを作成する方法
BizTalk Server 管理コンソールを使用して送信ポートを作成するには、次の手順を実行します。  
  
## <a name="creating-a-send-port"></a>送信ポートの作成  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。  
  
    2.  **型**ドロップダウン リストで、 **PeopleSoft**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
    6.  をクリックして**構成**送信ポートを構成します。  
  
4.  **PeopleSoft トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイルです。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用する****はい**です。  
  
    4.  **[OK]**をクリックします。  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)