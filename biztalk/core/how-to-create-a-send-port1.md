---
title: 送信 Port1 を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a0657f32edfbddd3830605d271daafc632db60d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385563"
---
# <a name="how-to-create-a-send-port"></a>送信ポートを作成する方法
JD Edwards EnterpriseOne の送信ポートを BizTalk Server を作成する次の手順を使用します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  送信ポート ノードを右クリックします。  
  
2.  クリックして**送信ポートの追加**します。  
  
3.  **新しい送信ポートを作成**ダイアログ ボックスで、**静的な送信請求-応答ポート**から、**送信ポートの種類を指定**ボックスの一覧し、をクリックして**OK**.  
  
     **静的な送信請求-応答送信ポートのプロパティ**ウィンドウが開きます。  
  
4.  たとえば、送信ポートの名前を入力`SSOSendToJDEEntOne`します。  
  
5.  クリックして**トランスポート**左側のウィンドウでします。  
  
6.  クリックして**トランスポートの種類**、選択および **[jdeentone]** します。  
  
7.  選択、**アドレス (URI)**、省略記号 (...) ボタンをクリックします。  
  
     JD Edwards EnterpriseOne**トランスポートのプロパティ** ダイアログ ボックスが表示されます。  
  
8.  型`myJDEEntOneSSO`の**論理システム名**します。  
  
9. 選択**はい**の**SSO を使用して、** します。  
  
10. ボックスの一覧では、JD Edwards EnterpriseOne システムを表すよう作成したシングル サインオン (SSO) 関連アプリケーションを選択します。  
  
     クリックして**OK**を入力した情報を確認します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications4.md)   
 [BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)