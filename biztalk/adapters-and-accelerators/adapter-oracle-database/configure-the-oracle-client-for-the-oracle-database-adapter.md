---
title: Oracle データベース アダプターの Oracle クライアントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a2186f4ea5400d01f477d0ab98c282e37e32d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376703"
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a>Oracle データベース アダプターの Oracle クライアントを構成します。
> [!IMPORTANT]
>  このトピックでは、Oracle データベースへの接続に tnsnames.ora を使用している場合にのみ該当します。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]はコンピューターにインストールされている Oracle クライアントを使用して Oracle データベースに接続します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Net サービス名を渡します Oracle データベースへの接続を確立するために Oracle クライアントへの接続 URI を指定します。 Net サービス名は、Oracle クライアントを使用して、ターゲットの Oracle データベースのサービスの接続情報を取得するエイリアスです。  
  
 Oracle クライアントを使用して構成されている名前付けの方法に従って、net サービス名を解決します。 Oracle クライアントで使用される名前付け方法を構成するのに Oracle Net Configuration Assistant を使用します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに接続するため、ローカルの名前付けのメソッドをサポートしています。 このメソッドは、net サービス名を解決するのには、tnsnames.ora、ローカル ファイルを使用します。  
  
 Tnsnames.ora ファイルは、net サービス名と接続、Oracle クライアントが特定の Oracle database service (インスタンス) への接続を確立するために必要な情報が含まれている記述子を関連付けます。 Tnsnames.ora からエントリの例を次に示します。  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 このエントリの例では、アダプターは、net サービス名です。 接続記述子では、アドレス情報、およびアダプターに関連付けられている Oracle データベースのサービスのサービス名を指定します。 Oracle Net Configuration Assistant を使用して、作成 tnsnames.ora で net サービス名を構成することができます。 Net サービス名を構成した後は、次の例に示す接続 URI で指定できます。  
  
```  
oracledb://ADAPTER  
```  
  
 Oracle Net Configuration Assistant の使用方法と tnsnames.ora の詳細については、Oracle データベース Net Services 管理者ガイド 』 を参照してください。 特定のインストールの構成の詳細についてデータベース管理者に問い合わせてください。  
  
## <a name="see-also"></a>参照  
[Oracle データベースへの接続の作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)