---
title: JD Edwards OneWorld アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac3c1d96de7faaf4200f9ee93387cc4a9a36933
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306419"
---
# <a name="troubleshooting-the-adapter"></a>アダプターのトラブルシューティング
このトピックでは、Microsoft BizTalk Adapter for JD Edwards OneWorld の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a>送信ポートおよび受信ポートのプロパティでワイルドカードを使用できない  
 Adapter for JD Edwards One World では、以下のプロパティ フィールドでのワイルドカードの使用をサポートしていません。  
  
|送信ポートのプロパティ|受信ポートのプロパティ|  
|------------------------|---------------------------|  
|Username|イベント ファイル パス|  
|JDE 環境|イベント ターゲット名のプレフィックス|  
|Host||  
|Port||  
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
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)     
 [JD Edwards OneWorld のトラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)