---
title: Oracle E-business Suite アダプターのクライアントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 842b6ecc-5334-4cc0-af10-baa7f692ad23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13c29eef73f5268571c9c9eb33635a0f336954f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375670"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a>Oracle E-business Suite アダプターのクライアントを構成します。
> [!IMPORTANT]
>  このトピックでは、Oracle データベースへの接続に tnsnames.ora を使用している場合にのみ該当します。  
  
 接続を確立するために、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アダプターがコンピューターにインストールされている Oracle クライアントを使用して基になる Oracle データベースに接続します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Net サービス名を渡します Oracle E-business Suite への接続を確立するために Oracle クライアントへの接続 URI を指定します。 Net サービス名は、Oracle クライアントを使用して、ターゲットの Oracle データベースのサービスの接続情報を取得するエイリアスです。  
  
 Oracle クライアントを使用して構成されている名前付けの方法に従って、net サービス名を解決します。 Oracle クライアントで使用される名前付け方法を構成するのに Oracle Net Configuration Assistant を使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するため、ローカルの名前付けのメソッドをサポートしています。 このメソッドは、net サービス名を解決するのには、tnsnames.ora、ローカル ファイルを使用します。  
  
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
oracleebs://ADAPTER  
```  
  
 Oracle Net Configuration Assistant の使用方法と tnsnames.ora の詳細については、Oracle データベース Net Services 管理者ガイド 』 を参照してください。 特定のインストールの構成の詳細についてデータベース管理者に問い合わせてください。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite への接続を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)