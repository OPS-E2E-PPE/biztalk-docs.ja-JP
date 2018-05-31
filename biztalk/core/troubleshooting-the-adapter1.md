---
title: JD Edwards EnterpriseOne アダプターのトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac716a7567930509ebfd310cdaf9874286b349c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013129"
---
# <a name="troubleshooting-the-adapter"></a>アダプターのトラブルシューティング
このトピックでは、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a>送信ポートのプロパティにワイルドカードを使用できない  
 Adapter for JD Edwards Enterprise One では、以下の送信ポート プロパティ フィールドにワイルドカードを使用できません。  
  
-   Username  
  
-   JDE 環境  
  
-   Host  
  
-   ポート  
  
-   Java_Home  
  
-   JDE JAR ファイル  
  
-   セキュリティ サーバー名  
  
-   サービス名接続  
  
-   Data Source Name  
  
-   データベースの所有者  
  
-   データベース サーバー名  
  
-   データベースの種類  
  
-   物理データベース名  
  
## <a name="connecting-to-oracle-database"></a>Oracle データベースへの接続  
 Oracle データベースを JD Edwards で使用する場合、jdeinterop.ini ファイルを変更する必要があります。 シングル サインオンを使用する場合、[JDBj-ORACLE] セクションは Oracle の tnsnames の場所を定義します。このデータベース パラメーターを使用する必要があります。また、SQLNET.ORA ファイルが BizTalk Server コンピューター上に存在する必要があります (このファイルは Oracle Client に付属しています)。  
  
 次の内容を jdeinterop.ini ファイルに追加します。  
  
1.  [JDBj-ORACLE] の下:   
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  [JDBj-BOOTSTRAP DATA SOURCE] の下:   
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>参照  
 [アダプターを追加し、アイテムを作成します。](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
 [JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md)