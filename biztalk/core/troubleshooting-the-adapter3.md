---
title: "トラブルシューティング、Adapter3 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], connecting [Oracle databases]
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], troubleshooting
- Oracle databases, connecting [JD Edwards OneWorld adapters]
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15197bcdc84e813d31a8d5292f5559aca1f8ae01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a>アダプターのトラブルシューティング
このトピックでは、Microsoft BizTalk Adapter for JD Edwards OneWorld の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a>送信ポートおよび受信ポートのプロパティでワイルドカードを使用できない  
 Adapter for JD Edwards One World では、以下のプロパティ フィールドでのワイルドカードの使用をサポートしていません。  
  
|送信ポートのプロパティ|受信ポートのプロパティ|  
|------------------------|---------------------------|  
|[ユーザー名]|イベント ファイル パス|  
|JDE 環境|イベント ターゲット名のプレフィックス|  
|Host||  
|ポート||  
|Java_Home||  
|JDE JAR ファイル||  
  
## <a name="connecting-to-oracle-database"></a>Oracle データベースへの接続  
 Oracle データベースを JD Edwards で使用する場合、jdeinterop.ini ファイルを変更する必要があります。 シングル サインオンを使用する場合、[JDBj-ORACLE] セクションは Oracle の tnsnames の場所を定義します。このデータベース パラメーターを使用する必要があります。また、SQLNET.ORA ファイルが BizTalk Server コンピューター上に存在する必要があります (このファイルは Oracle Client に付属しています)。  
  
 次の内容を jdeinterop.ini ファイルに追加します。  
  
1.  [JDBj-ORACLE] の下に、次のように入力します。  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  [JDBj-BOOTSTRAP DATA SOURCE] の下に、次のように入力します。  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld 用送信ポートを作成する方法](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md)   
 [JD Edwards OneWorld のトラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)