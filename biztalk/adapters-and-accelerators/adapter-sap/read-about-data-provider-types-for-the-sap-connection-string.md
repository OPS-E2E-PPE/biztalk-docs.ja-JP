---
title: "SAP 接続文字列のデータ プロバイダーの種類の説明を読む |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77219fb74b7af377953a3761c4d9f241b3a8bd0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a>SAP 接続文字列のデータ プロバイダーの種類の説明を読む
SAP システムへの接続を確立するには、ときは、接続文字列の形式で ADO.NET クライアントが SAP 接続のプロパティを指定してください。 SAP ADO 接続文字列の形式は、ようになります。  
  
```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  
  
 使用して SAP システムへの接続への接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次の種類を持つことができます。  
  
-   **タイプ a:**アプリケーション ホスト ベース接続を使用するアプリケーション サーバーを指定する接続 URI、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムに接続します。  
  
-   **タイプ b:**負荷分散の接続を経由するメッセージ サーバーを指定する接続 URI、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムに接続します。  
  
-   **種類 d:**先ベースの接続を接続 URI が SAP システムの接続パラメーターを含む saprfc.ini ファイルの保存先を指定します。  
  
 次の表では、接続 URI にこれらの接続を指定する方法について説明します。  
  
|TYPE|プロパティ 1|プロパティ 2|Description|  
|----------|----------------|----------------|-----------------|  
|A|ASHOST (アプリケーション サーバーのホスト)|SYSNR (SAP システム番号)|アプリケーション ホスト ベース接続を指定します。|  
|B|MSHOST (メッセージ サーバー ホスト)|R3NAME (SAP R3 名)|負荷分散のメッセージ サーバー経由の接続を指定します。 負荷分散の接続では、省略可能なサーバー グループを指定することができます。|  
|D|追加先 (宛先 saprfc.ini ファイルの接続パラメーターが含まれています)|-|移行先ベースの接続を指定します。 Saprfc.ini ファイルで指定したコピー先には、SAP 接続パラメーターが含まれています。 マップ先の型 A と B の種類の接続のみを指定できます。 **注:** saprfc.ini ファイルの接続の値を指定する場合は、ファイルにアクセスする .exe または SAP システムで必要とする標準の場所では、同じフォルダーに保存されていることを確認してください。 詳細については、SAP のマニュアルを参照してください。|  
  
 接続を使用して SAP システムへの接続への接続文字列の種類に基づいて、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のプロパティを含めることができます。  
  
|プロパティ|型の使用|Description|  
|--------------|-------------------|-----------------|  
|アプリケーション サーバーのホスト (ASHOST)|A|SAP アプリケーション サーバー ホストの名前です。|  
|システム番号 (SYSNR)|A|SAP システム番号|  
|アプリケーション サーバー グループ名 (グループ)|B|SAP サーバー グループの名前。 これは、負荷分散の接続内のアプリケーション サーバーの任意のグループです。|  
|メッセージ サーバー ホスト (MSHOST)|B|SAP メッセージ サーバー ホストの名前|  
|メッセージ サーバー サービス (MSSERV)|B|指定されている SAP メッセージ サーバー サービスの名前、\<システム ドライブ\>: \WINDOWS\system32\drivers\etc\services ファイル。 値を指定しない場合、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]これがあることを前提としています"いる sapms\<R/3 システム名\>"です。 たとえば、R/3 システム名が DV1 の場合は、アダプターはメッセージ サーバーのサービス名"sapmsDV1"であると仮定します。<br /><br /> ただし、サービス ファイルのエントリが異なる場合は、その値を指定する必要があります。|  
|R/3 システム名 (R3NAME)|B|SAP R/3 の名前です。|  
|移行先 (追加先)|D|Saprfc.ini ファイルから接続パラメーターを取得します。|  
|クライアント (クライアント)|A、B、D|SAP クライアント番号|  
|言語 (Lang)|A、B、D|言語|  
|パスワード (PASSWD)|A、B、D|SAP ユーザー パスワード|  
|ユーザー名 (ユーザー)|A、B、D|SAP システムに接続するユーザー名|  
|SAP GUI (AbapDebug) のデバッグを有効にします。|A、B、D|省略可能なパラメーターを指定するかどうかからデバッグを ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]が有効になって、アダプターは、SAP GUI を使用して、デバッグ用かどうかとします。 値を指定できます True または False です。True の場合、ABAP デバッグを有効にされ、SAP GUI が開かれます。 既定値は False です。|  
|トレースの RFC SDK(RfcSdkTrace)|A、B、D|RFC ライブラリ トレースが有効になっているかどうかを示す省略可能なパラメーターです。 値を指定できます True または False です。True の場合は、RFC ライブラリ トレースが有効にします。 既定値は False です。|  
  
> [!NOTE]
>  [プロパティ] 列では、かっこ内で提供される値は、プログラミング ソリューションを通じて接続 URI を提供する際に指定する必要があります接続のプロパティの名前です。 ただし、ADO インターフェイスを使用して、DDEX プラグインまたは SQL Server インポートおよびエクスポート ウィザードを使用している場合は、接続のプロパティがフレンドリ名として表示されます。  
  
## <a name="example-connection-string-for-type-a"></a>型の接続文字列の例 A  
 タイプ A の接続文字列の例は、ようになります。  
  
```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
> [!NOTE]
>  既定では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]常に考慮する種類 a への接続文字列  
  
## <a name="example-connection-string-for-type-b"></a>B の種類用の接続文字列の例  
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
  
 Saprfc.ini ファイルの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457)です。  
  
 すべての 3 つの接続の種類のパスワードは、二重引用符を含めることはできません。 ただし、パスワードの特殊文字が含まれている場合、パスワードを二重引用符で囲む必要があります。 例:  
  
```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  
  
> [!IMPORTANT]
>  1 つだけの接続の種類の A、B、または D. の接続パラメーターを指定する必要があります。たとえば、接続文字列で、アプリケーション サーバーのホストを指定する場合必要がありますいないを指定するメッセージ サーバーのホスト名または、R3NAME。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)