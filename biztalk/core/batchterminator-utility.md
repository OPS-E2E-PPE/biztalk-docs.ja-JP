---
title: BatchTerminator ユーティリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 080f82993fc3c8c62b3764d496f03589bd06364e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967352"
---
# <a name="batchterminator-utility"></a>BatchTerminator ユーティリティ
BatchTerminator ユーティリティを使用すると、EDI インターチェンジのバッチ処理に使用されているアクティブなバッチ処理オーケストレーションをすべて終了できます。 このユーティリティは、多数のバッチ処理オーケストレーション インスタンスを実行していて、BizTalk Server システムの保守を行うためにすべてのバッチを終了する必要があるときに便利です。  
  
 BatchTerminator ユーティリティは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator フォルダーにあります。 ユーティリティの batchterminator.log ファイルに結果が記録バッチ処理オーケストレーション インスタンスを終了するユーティリティを実行すると、 \<*ドライブ*\>: \Documents and 設定\\<*ユーザー名*\>\Application Data フォルダーです。  
  
> [!NOTE]
>  BatchTerminator ユーティリティは、32 ビット システムでのみサポートされます。  BatchTerminator では、Microsoft.BizTalk.ExplorerOM 名前空間のコンポーネントを使用します。この名前空間は、32 ビット プロセスから使用した場合にのみサポートされます。  
  
 **終了したオーケストレーション インスタンスを再起動します。**  
  
 バッチ処理オーケストレーションのグループを終了した後に、それらのオーケストレーション インスタンスをまとめて再開できます。 そのためには、/Activate スイッチと、停止されたバッチを示すファイルの名前とパスを使用します。 この停止バッチ ファイルは、ユーティリティを実行してオーケストレーション インスタンスのグループを終了したときに作成されます。 停止バッチ ファイルは batchsettings-\<GUID\>.xml、 \<*ドライブ*\>: \Documents and 設定\\<*ユーザー名* \>\Application data フォルダーです。 ログ ファイルには、停止バッチ ファイルのパスと名前も保存されます。 /activate スイッチを指定してユーティリティを実行すると、入力ファイルがスキーマに対して検証されます。  
  
 **構文**  
  
 BatchTerminator ユーティリティは、コマンド ライン ウィンドウで次の構文を使用して実行します。  
  
```  
BatchTerminator /<switch>  
```  
  
 BatchTerminator ユーティリティは、次のスイッチを指定して実行できます。 スイッチを指定しない場合、/terminate オプションが使用されます。 下に示すように、スイッチの完全な名前 (/terminate など) または短縮形 (/t など) を入力できます。  
  
|||  
|-|-|  
|スイッチ|関数|  
|/?|ヘルプを表示|  
|/終了のログ:\<*ログ ファイル*\><br /><br /> または/t-ログ:\<*ログ ファイル*\>|すべてのアクティブな X12 または EDIFACT バッチ処理オーケストレーション インスタンスに、終了コントロール メッセージを送信します。 終了されたすべてのアクティブなバッチ オーケストレーション インスタンスの一覧、見つかったアクティブなバッチ オーケストレーションの数、および送信された終了コントロール メッセージを含む操作結果が表示されます。 Batchterminator.log ファイルに結果がログに記録、 \<*ドライブ*\>: \Documents and 設定\\<*ユーザー名*\>\アプリケーション データ フォルダーです。<br /><br /> オプションの -log: パラメーターを使用すると、ログ ファイルの名前や、ログ ファイルを保存するフォルダーのパスを指定できます。 パスとファイル名を指定するパラメーターを使用しての例は、次:`BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`です。 このパラメーターを使用してファイル名だけを指定するには、`BatchTerminator.exe /terminate -log:log.txt` のようにします。 ユーティリティで、既定のパスを使用して指定されたパスが有効でない場合: \<*ドライブ*\>: \Documents and 設定\\<*ユーザー名*\>\Application データ。 -log: パラメーターは、/terminate スイッチを指定するかどうかにかかわらず使用できます。|  
|/print<br /><br /> または /p|終了コントロール メッセージを送信せずに、現在のアクティブなバッチ処理オーケストレーションの一覧を表示します。|  
|無効化/有効:\<*パス*\>\\<br />batchsettings-\<*GUID*\>.xml-ログ:\<*ログ ファイル*\><br /><br /> または/a:\<*パス*\>\\<br />batchsettings-\<*GUID*\>.xml-ログ:\<*ログ ファイル*\>|BatchSettings - に記載されている、以前に終了されたオーケストレーション インスタンスを再アクティブ化\<GUID\>.xml ファイルです。 入力ファイルが、コードに埋め込まれているスキーマに対して検証されます。 入力ファイルがスキーマと一致しない場合、画面にエラー メッセージが出力され、プログラムが終了します。<br /><br /> -log: スイッチを指定してこの操作を実行すると、再開処理に関する情報がログ ファイルに書き込まれます。|  
  
 **バッチ アクティベーション ファイルの形式**  
  
 以前の再アクティブ化を使用してバッチ オーケストレーション インスタンスを終了、/activate スイッチをバッチ アクティベーション ファイルを指定する必要があります (batchsettings-\<GUID\>.xml)。 このファイルは、次の形式にする必要があります。  
  
```  
<?xml version="1.0"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" elementFormDefault="qualified" id="BatchInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="BatchTerminator">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Batch">  
          <xs:complexType>  
            <xs:attribute name="PartyName" type="xs:string" />  
            <xs:attribute name="PartyID" type="xs:int" use="required" />  
            <xs:attribute name=”BatchName” type=”xs:string” />  
            <xs:attribute name=”BatchID” type=”xs:int” use=”required” />  
            <xs:attribute name="EdiMessageType" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-run-the-batchterminator-utility"></a>BatchTerminator ユーティリティを実行するには  
  
1.  Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator フォルダーに移動します。  
  
2.  Enter **BatchTerminator**必要なスイッチをなど、順にクリックして**Enter**です。  
  
3.  Windows エクスプローラで、移動\<*ドライブ*\>: \Documents and 設定\\<*ユーザー名*\>\Application Data フォルダー、およびbatchterminator.log ファイルを開いて、結果のログを参照してください。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)