---
title: BatchTerminator ユーティリティ |Microsoft Docs
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
ms.openlocfilehash: e64c14cc2c1ff7538f96275bb452f0ef643327c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358249"
---
# <a name="batchterminator-utility"></a>BatchTerminator ユーティリティ
BatchTerminator ユーティリティでは、EDI インターチェンジのバッチに使用されているライブのすべてのバッチ処理オーケストレーションを終了することができます。 このユーティリティは、多数のバッチ処理を実行しているオーケストレーション インスタンスがあるし、BizTalk server システムのメンテナンスを実行するには、すべてのバッチを終了する必要がある場合に役立つ可能性があります。  
  
 BatchTerminator ユーティリティにあります、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \utilities\microsoftedi\batchterminator フォルダー。 ユーティリティは batchterminator.log ファイルに、結果のログをバッチ処理オーケストレーション インスタンスを終了するユーティリティを実行すると、 \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\Application Data フォルダー。  
  
> [!NOTE]
>  BatchTerminator ユーティリティは 32 ビット システムでのみサポートされます。  BatchTerminator では、32 ビット プロセスから使用されている場合にのみサポートされている Microsoft.BizTalk.ExplorerOM 名前空間でコンポーネントを使用します。  
  
 **終了したオーケストレーション インスタンスを再起動します。**  
  
 バッチ処理オーケストレーションのグループを終了した後は、それらのオーケストレーション インスタンスをまとめて再開を行うことができます。 そのためには、/Activate スイッチと、名前と停止されたバッチを示すファイルのパス。 オーケストレーション インスタンスのグループを終了するユーティリティを実行すると、ユーティリティはこの停止バッチ ファイルを作成します。 停止バッチ ファイルは batchsettings-\<GUID\>で .xml、 \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名* \>\Application data フォルダー。 停止バッチ ファイルの名前とパスは、ログ ファイルも保存されます。 ユーティリティを実行すると、スイッチを入力ファイルがスキーマに対して検証します。  
  
 **構文**  
  
 BatchTerminator ユーティリティは、次の構文でのコマンド ライン ウィンドウで実行します。  
  
```  
BatchTerminator /<switch>  
```  
  
 BatchTerminator ユーティリティは、次のスイッチで実行できます。 スイッチが指定されていない場合、/terminate オプションを使用します。 下に示すように、スイッチの完全名を入力します。/終了すると、この場合は、短縮形または/t です。  
  
|||  
|-|-|  
|スイッチ|関数|  
|/?|ヘルプを表示します|  
|/終了 - ログ:\<*ログ ファイル*\><br /><br /> または/t-ログ:\<*ログ ファイル*\>|送信は、コントロール メッセージをすべてのアクティブな X12 または EDIFACT バッチ処理オーケストレーション インスタンスを終了します。 終了したすべてのアクティブなバッチ オーケストレーション インスタンスの一覧、見つかったアクティブなバッチ オーケストレーションの数、送信された終了コントロール メッセージの数など、操作の結果が表示されます。 Batchterminator.log ファイルに結果がログに記録、 \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\アプリケーション データ フォルダー。<br /><br /> オプションの-log: パラメーターでは、ログ ファイルの名前やログ ファイルに保存するフォルダーのパスを指定することができます。 パスとファイル名を指定するパラメーターを使用しての例は、次:`BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`します。 ファイル名を指定するパラメーターを使用しての例は、次をのみです:`BatchTerminator.exe /terminate -log:log.txt`します。 ユーティリティは、既定のパスを使用して、指定されたパスが有効でない場合: \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\Application データ。 -Log: パラメーターを付けても付けなくても使用できます、/terminate スイッチ。|  
|/print<br /><br /> または/p|終了コントロール メッセージを送信せずに、現在アクティブなバッチ処理オーケストレーション インスタンスの一覧を表示します|  
|/activate:\<*path*\>\\<br />batchsettings-\<*GUID*\>.xml-ログ:\<*ログ ファイル*\><br /><br /> または/a:\<*パス*\>\\<br />batchsettings-\<*GUID*\>.xml-ログ:\<*ログ ファイル*\>|BatchSettings に記載されている以前に終了されたオーケストレーション インスタンスを再アクティブ化\<GUID\>.xml ファイルです。 入力ファイルのコードに埋め込まれているスキーマに対して検証されます。 入力ファイルで、スキーマが一致しない場合、エラー メッセージは、画面に出力して、プログラムが終了します。<br /><br /> この操作は、含める場合は、ログ ファイルで再起動アクションに関する情報を書き込みます-log: スイッチします。|  
  
 **バッチ アクティベーション ファイルの形式**  
  
 以前の再アクティブ化を使用してバッチ オーケストレーション インスタンスを終了、/activate スイッチをバッチ アクティベーション ファイルを提供する必要があります (batchsettings-\<GUID\>.xml)。 このファイルは、次の形式にする必要があります。  
  
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
  
1. Windows エクスプ ローラーで、移動、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \utilities\microsoftedi\batchterminator フォルダー。  
  
2. Enter **BatchTerminator**し、必要なスイッチと共にクリックして **」と入力**します。  
  
3. Windows エクスプ ローラーで、移動\<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\Application Data フォルダー、および結果のログを表示する batchterminator.log ファイルを開きます。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)