---
title: データ プロバイダーのプロパティの Siebel 接続文字列 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- conncting, to the Siebel system
- Data Provider for Siebel, connection string
ms.assetid: 8ab0c29e-e06b-4e74-be4e-9aa862a05539
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1caedbc1e9560c1bc4d97669241046f0959c2db6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222218"
---
# <a name="data-provider-properties-for-the-siebel-connection-string"></a>Siebel の接続文字列のデータ プロバイダーのプロパティ
[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) を使用して、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムにアクセスします。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]順番 Siebel システムにアクセスする Siebel COM データ コントロール ライブラリを使用します。 Siebel COM データ コントロールは、Siebel Web クライアントに付属します。  
  
 Siebel システムへの接続を確立するには、ADO.NET クライアントがデータベース接続文字列をエンコードして Siebel 接続のプロパティを指定してください。 これが必要な[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]実装**DbConnection**へのアクセス、基になる[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドします。  
  
 使用して Siebel システムへの接続への接続文字列、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次のプロパティが含まれています。  
  
|プロパティ|Description|  
|--------------|-----------------|  
|Password|Siebel システムのユーザーのパスワードこの値は大文字小文字を区別します。 **注:** 、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel システム上の接続が開くときにパスワードを入力する値の大文字小文字を保持します。|  
|[ユーザー名]|Siebel システムでのユーザー名この値は大文字小文字を区別します。 **注:** 、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel システム上の接続が開くときに、ユーザー名を入力する値の大文字小文字を保持します。|  
|圧縮|間で使用する圧縮アルゴリズム、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と Siebel システムです。 サポートされる値は**none**または**zlib**です。 このパラメーターはオプションです。 Siebel システムが既定値を提供することが指定されていない場合 (**zlib**)。|  
|暗号化|間で使用する暗号化の種類、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と Siebel システムです。 サポートされる値は**none**、 **mscrypto**、または**rsa**です。 このパラメーターはオプションです。 Siebel システムが既定値を提供することが指定されていない場合 (**none**)。|  
|言語|オブジェクト マネージャーの言語です。 例の値は**日本語**です。 このパラメーターは必須です。|  
|SiebelEnterpriseServer|Siebel エンタープライズ サーバーの名前。 このパラメーターは必須です。|  
|SiebelGateway|Siebel サーバーの IP とポートで構成されます。 たとえば、Siebel_Server:1234 です。|  
|SiebelObjectManager|エンタープライズ サーバー上の Siebel オブジェクト マネージャーの名前。 このパラメーターは必須です。|  
|SiebelRepository|Siebel リポジトリ。 複数のリポジトリがサーバー上に存在するかどうかに必要なそれ以外の場合、省略可能です。 **注:** サーバーで複数のリポジトリが存在する場合は、SiebelRepository パラメーターで、ターゲットのリポジトリを指定する必要があります。|  
|SiebelServer|Siebel サーバーです。 必要なすべての Siebel 7.5 サーバー接続です。それ以外の場合、このパラメーターを設定しません。|  
|[Transport]|トランスポートです。のみ**tcpip**はサポートされています。 このパラメーターはオプションです。 Siebel システムが既定値を提供することが指定されていない場合 (**tcpip**)。|  
  
 例:  
  
```  
Username=YourUserName;Password=YourPassword;SiebelGateway=Siebel_Server:1234;SiebelObjectManager=obj_mgr;SiebelEnterpriseServer=ent_server;Language=enu;SiebelRepository=siebel_rep  
```  
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)