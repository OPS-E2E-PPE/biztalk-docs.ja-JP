---
title: "送信 Port1 を作成する方法 |Microsoft ドキュメント"
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
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61c82b199f7b8686556f2cbb53a90b0d4b59536e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a>送信ポートを作成する方法
JD Edwards EnterpriseOne 用の BizTalk Server 送信ポートを作成するには、次の手順を使用します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  [送信ポート] ノードを右クリックします。  
  
2.  をクリックして**送信ポートの追加**です。  
  
3.  **新しい送信ポートを作成**ダイアログ ボックスで、**静的な送信請求-応答ポート**から、**送信ポートの種類の指定**ボックスの一覧し、をクリックして**OK**.  
  
     **静的な送信請求-応答送信ポート プロパティ**ウィンドウが開きます。  
  
4.  たとえば、送信ポートの名前を入力`SSOSendToJDEEntOne`です。  
  
5.  をクリックして**トランスポート**左側のウィンドウでします。  
  
6.  をクリックして**トランスポートの種類**を選択して**[jdeentone]**です。  
  
7.  選択、**アドレス (URI)**、省略記号 (...) ボタンをクリックします。  
  
     JD Edwards EnterpriseOne**トランスポートのプロパティ** ダイアログ ボックスが表示されます。  
  
8.  型`myJDEEntOneSSO`の**論理システム名**です。  
  
9. 選択**はい**の**SSO を使用して**です。  
  
10. 一覧で、JD Edwards EnterpriseOne システムを表すよう作成したシングル サインオン (SSO) 関連アプリケーションを選択します。  
  
     をクリックして**OK**入力した情報を確認します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications4.md)   
 [シングル サインオンを使用します。](../core/using-single-sign-on1.md)