---
title: ダブル アクション PIPAutomation オーケストレーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9159f7b1-cb83-41f1-8637-39c5ddcc63ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f04b04d20189307c3d42e60c43c2c4c9254ffb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008427"
---
# <a name="double-action-pipautomation-orchestration"></a>ダブル アクション PIPAutomation オーケストレーション
DoubleAction.odx のサンプルは、オーケストレーションを実装し、ダブルアクションの PIP (Partner Interface Process) である 0C2、0C4、3A2、および 3A40 に対する応答を自動的に生成する方法を示します。 このサンプル プロジェクトを拡張し、さらに多くのダブルアクション PIP をサポートすることもできます。  
  
> [!NOTE]
>  サンプル フォルダーに入っているマップはサンプルです。 これらを使用するには、特定の要件に応じて変更する必要があります。  
  
> [!NOTE]
>  シングルアクション PIP ではなく、ダブルアクション PIP のみをサポートするように、このサンプルを拡張してください。 このオーケストレーションは、シングルアクション PIP を処理するように拡張すると、エラーを返します。 このオーケストレーションがシングルアクション PIP を処理しないように、次の「シングルアクション メッセージのフィルタリング」を参照してください。  
  
 既定では、Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップ プログラムによってこのサンプルで\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction します。  
  
 このサンプル プロジェクトには次のものが含まれています。  
  
- ストアド プロシージャ (`PipAutomationGetAction)`メッセージを取得する新しいアクション Pip の 0c2、0 C 4、3 a 2、および 3A4 します。  
  
- SQL ストアド プロシージャにバインドされた受信場所 (MessagesToLOB_Receive_Location)  
  
- 各 PIP を処理するオーケストレーション (DoubleAction.odx) は、各 PIP のマップを基に適切な応答を生成して、それを BTARNDATA データベースの MessagesFromLOB テーブルに保存します。 オーケストレーションは Microsoft.Solutions.BTARN.Shared.dll の `RNIFSubmit` メソッドを使用してメッセージを送信します。  
  
- Setup.bat ファイルが DoubleAction オーケストレーションで使用する MessagesToLOB_Receive_Port の作成に使用するバインド ファイル (DoubleActionBinding.xml)。  
  
- サンプルをビルドし、初期化するセットアップ ファイル。 BizTalk Server が 32 ビット コンピューターで実行している場合は、setup.bat ファイルを実行、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction フォルダーに移動します。 BizTalk Server が 64 ビット コンピューターで実行している場合は、同じフォルダーにある setupx64.bat を実行します。  
  
  オーケストレーションは、BTARNData データベースの PipAutomationGetAction ストアド プロシージャを使用してメッセージを受信します (ソース ファイルは DoubleAction ディレクトリ内の DoubleAction.sql)。 このストアド プロシージャは MessagesToLOB テーブルからメッセージを取得します。  
  
  このサンプル プロジェクトを拡張してダブルアクション PIP のサポートを追加するには、オーケストレーションにダブルアクション PIP のパスを追加します。 このパスには、要求メッセージに対する応答メッセージを構成するマップが含まれます。 たとえば、マップを参照してください、 [3 a 2 応答のマップ サンプルを 3 a 2 要求](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)と[3A4 要求から 3A4 応答のマップ サンプルへ&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)します。  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. コマンド プロンプトで、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー。  
  
   > [!NOTE]
   >  セットアップ プログラムを実行する前に、メモ帳で DoubleAction.sql ファイル (上記のフォルダー内) を開きます。 **ファイル** メニューのをクリックして**付けて**します。 **エンコード**一覧で、[ **ANSI**、] をクリックし、**保存**します。 をクリックして**はい**既存のファイルを上書きします。  
  
2. BizTalk Server が 32 ビット コンピューターで実行している場合は、setup.bat ファイルを実行、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー。 BizTalk Server のインストールが 64 ビット コンピューターで実行している場合は、同じフォルダーに setupx64.bat を実行します。 バッチ ファイルによって、次の処理が実行されます。  
  
   - BTARNDATA データベースに、MessagesToLOB テーブルからアクション メッセージを取得する SQL ストアド プロシージャ (`PipAutomationGetAction`) を作成します。 これによって、取得したレコードが再び読み取られることもなくなります。  
  
   - HeaderHelper [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
   - BizTalk Server SQL 受信ポートを作成してバインドします (MessagesToLOB_Receive_Port)。  
  
   - 受信場所 (MessagesToLOB_Receive_Location) を有効にします。  
  
   - ダブルアクション PIPAutomation オーケストレーション (DoubleAction.odx) をコンパイルし、展開します。  
  
   - BizTalk Server オーケストレーションをバインドして開始します。  
  
     > [!NOTE]
     >  コンパイル中に警告がいくつか表示されます。 これらの警告は無視してかまいません。  
  
     > [!NOTE]
     >  サンプルが既定のホスト名を使用して**BizTalkServerApplication**プロジェクトをデプロイするときにします。 別のホストのサンプルを実行するには、下の DoubleActionBinding.xml で既定のホスト名を編集する必要があります\<SDK\>\PIPAutomation\DoubleAction フォルダ。  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a>ダブルアクション PIPAutomation サンプルを実行するには  
  
1. ホーム ロールが開始側の 3A4 アグリーメントを作成します。 ホーム組織の GBI を 123456789 に設定し、パートナーの GBI を 987654321 に設定します。 この設定により、SDK の LOBApplication フォルダーの下の SampleInstances フォルダーにあるサンプルを使用できるようになります。  
  
2. ループバック アグリーメント ミラー ユーティリティを使用して、手順 1. で作成した 3A4 PIP のミラーを作成します。  
  
3. LOBApplication.exe SDK ユーティリティを使用して、3A4 PIP 要求メッセージを送信します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK にはフォルダーに入力のサンプルが含まれています\<*インストール ディレクトリ*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml します。  
  
4. BTARNDATA データベースでは、次のクエリを実行します。  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. 数秒後に、4 つの新しいメッセージがこのテーブルに表示されます。 そのうち 2 つは受信確認シグナルです。 1 つのシグナルは Async 3A4 要求メッセージです。 1 つのシグナルは Async 3A4 応答メッセージです。  
  
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を再度実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="remarks"></a>コメント  
 パブリック オーケストレーションは受信確認 (ACK および NACK シグナル メッセージ) を自動生成します。 基幹業務 (LOB) アプリケーションで作成する必要はありません。  
  
 MessagesFromLOB テーブルにルーティングされるメッセージの形式を LOBMessage と呼びます。 スキーマは、C:\Program files \microsoft BizTalk Accelerator RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd for で使用できます。 `RNIFSubmit` メソッドを使用する場合は、メッセージの形式を調整する必要はありません。 ServiceContent に追加情報を含めて送信するだけです。 `RNIFSubmit` によって MessagesFromLOB テーブルにレコードが生成されます。  
  
## <a name="filtering-out-single-action-messages"></a>シングルアクション メッセージのフィルタリング  
 このオーケストレーションはダブルアクション メッセージのみを受信します。 このサンプル プロジェクトがシングルアクション PIP をサポートするように拡張しないでください。 このオーケストレーションを使用してシングルアクション メッセージを処理しようとすると、エラーが表示されます。 オーケストレーションがシングルアクション メッセージを受信しないようにするには、PIPAutomationGetAction ストアド プロシージャの次の行を変更してください。  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 上記の行に WHERE 句を追加すると、シングルアクション メッセージがフィルタで除外されます。 処理するシングルアクション メッセージのすべてに WHERE 句を含めます。 行は、次のようにする必要があります。  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a>参照  
 [3 a 2 要求を 3 a 2 応答のマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)   
 [3A4 要求から 3A4 応答のマップ サンプルへ](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)