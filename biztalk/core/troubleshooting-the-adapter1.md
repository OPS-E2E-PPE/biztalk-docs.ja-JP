---
title: JD Edwards EnterpriseOne アダプターのトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 1d6ba3fdb8789f7d258291aee05d9e7b481e905a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306391"
---
# <a name="troubleshooting-the-adapter"></a>アダプターのトラブルシューティング
このトピックでには、特定し、JD Edwards EnterpriseOne の Microsoft BizTalk Adapter の使用中に発生する可能性がある問題を解決するのに役立つ情報が含まれています。  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a>送信ポートのプロパティでワイルドカードを使用することはできません。  
 JD Edwards Enterprise One 用のアダプターでは、次の送信ポート プロパティ フィールドにワイルドカードを使用することはできません。  
  
-   Username  
  
-   JDE 環境  
  
-   ホスト  
  
-   Port  
  
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
  
1.  [JDBJ-ORACLE]:   
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  [JDBJ-BOOTSTRAP DATA SOURCE]:   
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>参照  
 [アダプターを追加し、成果物を作成](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
 [JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md)