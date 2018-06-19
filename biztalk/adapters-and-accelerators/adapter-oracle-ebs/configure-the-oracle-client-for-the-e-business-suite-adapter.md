---
title: Oracle クライアント E-business Suite アダプターを構成する |Microsoft ドキュメント
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
ms.openlocfilehash: ada64bf6f54c95f3d6e1c8f968a506476dbbc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214770"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a>Oracle クライアント E-business Suite アダプターを構成します。
> [!IMPORTANT]
>  ここでは、Oracle データベースへの接続に tnsnames.ora を使用している場合にのみ該当します。  
  
 接続を確立するために、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アダプターがコンピューターにインストールされている Oracle クライアントを通じて基になる Oracle データベースに接続します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Net サービス名を渡します Oracle E-business Suite への接続を確立するために Oracle クライアントへの接続 URI を指定します。 Net サービス名は、Oracle クライアントが、ターゲットの Oracle データベースのサービスの接続情報の取得に使用するエイリアスです。  
  
 Oracle クライアントは、名前付け方法に従って、net サービス名を使用して構成されていることを解決します。 使用する Oracle Net Configuration Assistant、Oracle クライアントによって使用される名前付け方法を構成します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するため、ローカルの名前付けのメソッドをサポートしています。 このメソッドは、net サービス名を解決するのには、ローカル ファイル、tnsnames.ora を使用します。  
  
 Tnsnames.ora ファイルは、net サービス名を Oracle クライアントが特定の Oracle データベース service (インスタンス) への接続を確立するために必要な情報を含む記述子の接続を関連付けます。 Tnsnames.ora からサンプルのエントリを次に示します。  
  
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
  
 このサンプルのエントリでは、アダプターは、net サービス名です。 接続記述子は、アドレス情報と、サービスのサービス名、Oracle データベース アダプターに関連付けられているを指定します。 Oracle Net Configuration Assistant を使用して、作成 tnsnames.ora で net サービス名を構成することができます。 Net サービス名を構成した後は、次の例のように接続 URI で指定できます。  
  
```  
oracleebs://ADAPTER  
```  
  
 Oracle Net Configuration Assistant を使用して tnsnames.ora についての詳細については、Oracle データベース Net Services 管理者ガイド 』 を参照してください。 特定のインストールの構成の詳細についてデータベース管理者に問い合わせてください。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite への接続を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)