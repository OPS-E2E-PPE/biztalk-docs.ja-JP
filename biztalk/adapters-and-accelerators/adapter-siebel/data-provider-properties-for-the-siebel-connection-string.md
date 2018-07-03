---
title: Siebel 接続文字列のデータ プロバイダーのプロパティ |Microsoft Docs
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
ms.openlocfilehash: 0954cbec3c2dbd044037cc817a8ef97b1250bf8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988827"
---
# <a name="data-provider-properties-for-the-siebel-connection-string"></a>Siebel 接続文字列のデータ プロバイダーのプロパティ
[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) を使用して、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムにアクセスします。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]順番 Siebel システムにアクセスする Siebel COM データ コントロール ライブラリを使用します。 Siebel COM のデータ コントロールは、Siebel Web クライアントに付属します。  

 Siebel システムへの接続を確立するには、ADO.NET クライアントはデータベース接続文字列にエンコードされている Siebel 接続プロパティを指定する必要があります。 これは、必要なため、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]実装**DbConnection** 、基になるへのアクセスに[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドします。  

 使用して Siebel システムへの接続への接続文字列、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次のプロパティが含まれています。  


|        プロパティ        |                                                                                                                                                     説明                                                                                                                                                      |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        パスワード        |            Siebel システムのユーザーのパスワードこの値は大文字小文字を区別します。 **注:** 、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel システム上の接続を開くときにパスワードを入力する値の大文字小文字を保持します。             |
|        Username        |                  Siebel システムのユーザー名この値は大文字小文字を区別します。 **注:** 、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel システム上の接続を開くときにユーザー名を入力する値の大文字小文字を保持します。                  |
|      圧縮       |      間で使用する圧縮アルゴリズム、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と Siebel システム。 サポートされる値は**none**または**zlib**します。 このパラメーターはオプションです。 Siebel システムが既定値を提供することが指定されていない場合 (**zlib**)。       |
|       暗号化       | 間で使用する暗号化の種類、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と Siebel システム。 サポートされる値は**none**、 **mscrypto**、または**rsa**します。 このパラメーターはオプションです。 Siebel システムが既定値を提供することが指定されていない場合 (**none**)。 |
|        [言語]        |                                                                                                             オブジェクト マネージャーの言語です。 例の値は**日本語**します。 このパラメーターは必須です。                                                                                                             |
| SiebelEnterpriseServer |                                                                                                                        Siebel エンタープライズ サーバーの名前。 このパラメーターは必須です。                                                                                                                         |
|     SiebelGateway      |                                                                                                                     Siebel サーバーの IP とポートで構成されます。 たとえば、Siebel_Server:1234 です。                                                                                                                      |
|  SiebelObjectManager   |                                                                                                             Enterprise server、Siebel オブジェクト マネージャーの名前。 このパラメーターは必須です。                                                                                                              |
|    SiebelRepository    |                                     Siebel リポジトリ。 サーバーでは、複数のリポジトリが存在するかどうかに必要なそれ以外の場合、省略可能です。 **注:** サーバーでは、複数のリポジトリが存在する場合は、SiebelRepository パラメーターで、ターゲットのリポジトリを指定する必要があります。                                      |
|      SiebelServer      |                                                                                                       Siebel サーバーです。 必要なすべての Siebel 7.5 サーバー接続。それ以外の場合、このパラメーターを設定しないでください。                                                                                                       |
|       [Transport]        |                                                                               トランスポート。のみ**tcpip**はサポートされています。 このパラメーターはオプションです。 Siebel システムが既定値を提供することが指定されていない場合 (**tcpip**)。                                                                                |

 以下に例を示します。  

```  
Username=YourUserName;Password=YourPassword;SiebelGateway=Siebel_Server:1234;SiebelObjectManager=obj_mgr;SiebelEnterpriseServer=ent_server;Language=enu;SiebelRepository=siebel_rep  
```  

## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for Siebel eBusiness Applications を使用する](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)