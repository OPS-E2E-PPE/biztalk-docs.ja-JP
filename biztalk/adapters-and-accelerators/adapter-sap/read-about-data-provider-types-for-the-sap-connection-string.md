---
title: SAP 接続文字列のデータ プロバイダーの種類について確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c21602308a8163e81d04e60474072d521554a5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373092"
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a>SAP 接続文字列のデータ プロバイダーの種類をについてください。
SAP システムへの接続を確立するために、ADO.NET クライアントは接続文字列の形式で SAP 接続プロパティを指定する必要があります。 SAP の ADO 接続文字列の形式は、ようになります。  

```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  

 SAP システムを使用して接続する接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次の種類を持つことができます。  

- **タイプ A:** アプリケーションのホスト ベース接続を使用して、アプリケーション サーバーを指定する接続 URI、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]は SAP システムに接続します。  

- **型 B:** 負荷分散された接続 URI の接続が経由するメッセージ サーバーを指定します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]は SAP システムに接続します。  

- **型の D:** 宛先に基づく接続接続 URI が、SAP システムの接続パラメーターを含む saprfc.ini ファイルの宛先を指定します。  

  次の表では、接続 URI でこれらの接続を指定する方法について説明します。  

|TYPE|プロパティ 1|プロパティ 2|説明|  
|----------|----------------|----------------|-----------------|  
|A|ASHOST (アプリケーション サーバーのホスト)|SYSNR (SAP システム数)|アプリケーションのホスト ベース接続を指定します。|  
|B|MSHOST (メッセージ サーバー ホスト)|R3NAME (SAP R3 名)|負荷分散のメッセージ サーバー経由の接続を指定します。 を負荷の接続を分散する場合、省略可能なサーバー グループを指定できます。|  
|D|DEST (Destination saprfc.ini ファイルの接続パラメーターが含まれています)|-|移行先ベースの接続を指定します。 Saprfc.ini ファイルで指定したコピー先は、SAP 接続パラメーターに格納されます。 マップ先では、タイプ A および B の種類の接続のみを指定できます。 **注:** Saprfc.ini ファイルの接続値を指定する場合、ファイルにアクセスする .exe または SAP システムで必要と標準的な場所にある同じフォルダーに保存されていることを確認します。 詳細については、SAP のマニュアルを参照してください。|  

 SAP システムを使用して接続する接続文字列、接続の種類に基づいて、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のプロパティを含めることができます。  


|               プロパティ                | 型の使用 |                                                                                                                                                                                                                                               説明                                                                                                                                                                                                                                                |
|---------------------------------------|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   アプリケーション サーバーのホスト (ASHOST)    |       A       |                                                                                                                                                                                                                                 SAP アプリケーション サーバーのホストの名前。                                                                                                                                                                                                                                 |
|         システム番号 (SYSNR)         |       A       |                                                                                                                                                                                                                                          SAP システム番号                                                                                                                                                                                                                                           |
| アプリケーション サーバー グループ名 (グループ) |       B       |                                                                                                                                                                                              SAP サーバーのグループの名前。 これは、負荷分散接続内のアプリケーション サーバーの任意のグループです。                                                                                                                                                                                              |
|     メッセージ サーバー ホスト (MSHOST)      |       B       |                                                                                                                                                                                                                                   SAP メッセージ サーバー ホストの名前                                                                                                                                                                                                                                    |
|    メッセージ サーバー サービス (MSSERV)    |       B       | 指定されている SAP メッセージ サーバー サービスの名前、\<システム ドライブ\>: \WINDOWS\system32\drivers\etc\services ファイル。 値を指定しない場合、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]これがあることを前提としています"sapms\<R/3 システム名\>"。 たとえば、R/3 システム名が DV1 の場合は、アダプターはメッセージ サーバーのサービス名"sapmsDV1"にすると仮定します。<br /><br /> ただし、サービス ファイルのエントリが異なる場合は、その値を指定する必要があります。 |
|       R/3 システム名 (R3NAME)        |       B       |                                                                                                                                                                                                                                            SAP r/3 システム名。                                                                                                                                                                                                                                             |
|          移行先 (宛先)           |       D       |                                                                                                                                                                                                                        Saprfc.ini ファイルからの接続パラメーターを取得します。                                                                                                                                                                                                                         |
|            クライアント (クライアント)            |     A、B、D     |                                                                                                                                                                                                                                          SAP クライアント番号                                                                                                                                                                                                                                           |
|            (言語) 言語            |     A、B、D     |                                                                                                                                                                                                                                                 [言語]                                                                                                                                                                                                                                                 |
|           パスワード (パスワード)           |     A、B、D     |                                                                                                                                                                                                                                          SAP ユーザーのパスワード                                                                                                                                                                                                                                           |
|            ユーザー名 (ユーザー)            |     A、B、D     |                                                                                                                                                                                                                                SAP システムに接続するユーザー名                                                                                                                                                                                                                                 |
| SAP の GUI (AbapDebug) のデバッグを有効にします。  |     A、B、D     |                                                                                      省略可能なパラメーターを指定するかどうか ABAP からデバッグを[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を有効にし、デバッグするため、アダプターが、SAP GUI を使用するかどうか。 値は True または False です。True の場合は、ABAP デバッグを有効にされ、SAP GUI が開かれます。 既定値は False です。                                                                                      |
|      Trace RFC SDK(RfcSdkTrace)       |     A、B、D     |                                                                                                                                                                 RFC ライブラリ トレースが有効になっているかどうかを指定する省略可能なパラメーター。 値は True または False です。True の場合は、RFC ライブラリ トレースが有効にします。 既定値は False です。                                                                                                                                                                 |

> [!NOTE]
>  [プロパティ] 列では、かっこ内で提供される値は、プログラミング ソリューション経由の接続 URI を提供するときに、指定する必要があります接続のプロパティの名前です。 ただし、ADO インターフェイスを使用して、DDEX プラグインまたは SQL Server インポートおよびエクスポート ウィザードを使用する場合、接続のプロパティは、フレンドリ名として表示されます。  

## <a name="example-connection-string-for-type-a"></a>型の接続文字列の例 A  
 タイプ A の接続文字列の例は、ようになります。  

```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  

> [!NOTE]
>  既定では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]タイプ a のある接続文字列を常に考慮  

## <a name="example-connection-string-for-type-b"></a>タイプ B の接続文字列の例  
 タイプ B の接続文字列の例は、ようになります。  

```  
TYPE=B; R3NAME=NAME1; GROUP=ADAPTER; MSHOST=MSSERVER; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  

## <a name="example-connection-string-for-type-d"></a>種類 D の接続文字列の例  
 種類 D の接続文字列の例は、ようになります。  

```  
TYPE=D; DEST=TESTSAPSRV; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  

 Saprfc.ini ファイルの例のようになります。  

```  
DEST=TESTSAPSRV  
TYPE=A  
ASHOST=ADAPSAP47  
SYSNR=00  
```  

 Saprfc.ini ファイルの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457)します。  

 すべての 3 つの接続の種類のパスワードは、二重引用符を含めることはできません。 ただし、パスワードに他の特殊文字が含まれている場合、パスワードを二重引用符で囲む必要があります。 以下に例を示します。  

```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  

> [!IMPORTANT]
>  1 つだけの接続の種類の A、B、または D. の接続パラメーターを指定する必要があります。たとえば、接続文字列で、アプリケーション サーバーのホストを指定する場合はメッセージ サーバー ホスト名をまたは、R3NAME をしない指定する必要があります。  

## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)