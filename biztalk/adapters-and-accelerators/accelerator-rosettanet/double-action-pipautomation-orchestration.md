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
ms.openlocfilehash: 830846dd25bef7748fb6bcf77a112c03c3a152ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283741"
---
# <a name="double-action-pipautomation-orchestration"></a>ダブル アクション PIPAutomation オーケストレーション
DoubleAction.odx サンプルは、ダブル アクションの Partner Interface Process (Pip) の応答を自動的に生成するためのオーケストレーションを実装する方法を示しています。 0c2、0 C 4、3 a 2、3A4 とします。 追加のダブル アクション Pip をサポートするには、このサンプル プロジェクトを拡張することができます。  
  
> [!NOTE]
>  サンプル フォルダーに用意されているマップはサンプルです。 これらを使用するには、特定の要件に基づいてそれらを変更する必要があります。  
  
> [!NOTE]
>  ダブル アクション Pip のみ、いないシングル アクション Pip をサポートするには、このサンプル プロジェクトを拡張する必要があります。 シングル アクション PIP を処理するように拡張する場合、このオーケストレーションはエラーを返します。 このオーケストレーションがシングル アクション Pip を処理しないことを確認するには、後述の「シングル アクション メッセージをフィルター処理を参照してください。  
  
 既定では、Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップ プログラムによってこのサンプルで\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction します。  
  
 このサンプル プロジェクトが含まれます。  
  
- ストアド プロシージャ (`PipAutomationGetAction)`メッセージを取得する新しいアクション Pip の 0c2、0 C 4、3 a 2、および 3A4 します。  
  
- 受信場所 (MessagesToLOB_Receive_Location) は、SQL ストアド プロシージャにバインドします。  
  
- 各 PIP を処理するオーケストレーション (DoubleAction.odx) は、各 PIP のマップに基づく適切な応答を生成し、応答を BTARNDATA データベースの MessagesFromLOB テーブルに保存します。 オーケストレーションを使用して、`RNIFSubmit`メッセージを送信する Microsoft.Solutions.BTARN.Shared.dll からメソッド。  
  
- Setup.bat ファイルは DoubleAction オーケストレーションで使用する MessagesToLOB_Receive_Port の作成を使用してバインド ファイル (DoubleActionBinding.xml)。  
  
- セットアップ ファイル、サンプルをビルドして初期化します。 BizTalk Server が 32 ビット コンピューターで実行している場合は、setup.bat ファイルを実行、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction フォルダーに移動します。 BizTalk Server が 64 ビット コンピューターで実行している場合は、同じフォルダーにある setupx64.bat を実行します。  
  
  オーケストレーションでは、(ソース ファイルは、DoubleAction ディレクトリ内の DoubleAction.sql が)、BTARNData データベースの PipAutomationGetAction ストアド プロシージャを使用してメッセージを受信します。 このストアド プロシージャは MessagesToLOB テーブルからメッセージを取得します。  
  
  追加のダブル アクション Pip をサポートするには、このサンプル プロジェクトを拡張するには、ダブル アクション PIP のオーケストレーションで、パスを追加します。 このパスは、要求メッセージに対する応答メッセージを構成するマップが含まれます。 たとえば、マップを参照してください、 [3 a 2 応答のマップ サンプルを 3 a 2 要求](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)と[3A4 要求から 3A4 応答のマップ サンプルへ&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)します。  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. コマンド プロンプトで、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー。  
  
   > [!NOTE]
   >  セットアップ プログラムを実行する前にメモ帳で DoubleAction.sql (上記のフォルダー) 内のファイルを開きます。 **ファイル** メニューのをクリックして**付けて**します。 **エンコード**一覧で、[ **ANSI**、] をクリックし、**保存**します。 をクリックして**はい**既存のファイルを上書きします。  
  
2. BizTalk Server が 32 ビット コンピューターで実行している場合は、setup.bat ファイルを実行、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー。 BizTalk Server のインストールが 64 ビット コンピューターで実行している場合は、同じフォルダーに setupx64.bat を実行します。 バッチ ファイルでは、次の操作が実行されます。  
  
   - SQL ストアド プロシージャを作成します (`PipAutomationGetAction`)、アクション メッセージを MessagesToLOB テーブルから取得する、BTARNDATA データベースです。 こう取得したレコードは再び読み取られます。  
  
   - コンパイル、HeaderHelper[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]プロジェクトし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
   - 作成し、バインド、BizTalk Server SQL 受信ポート (MessagesToLOB_Receive_Port)。  
  
   - 受信場所 (MessagesToLOB_Receive_Location) を有効にします。  
  
   - コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。  
  
   - バインドし、BizTalk Server オーケストレーションを開始します。  
  
     > [!NOTE]
     >  サンプルでは、コンパイル中にいくつかの警告が表示されます。 これらの警告を無視することができます。  
  
     > [!NOTE]
     >  サンプルが既定のホスト名を使用して**BizTalkServerApplication**プロジェクトをデプロイするときにします。 別のホストのサンプルを実行するには、下の DoubleActionBinding.xml で既定のホスト名を編集する必要があります\<SDK\>\PIPAutomation\DoubleAction フォルダ。  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a>ダブル アクション PIPAutomation サンプルを実行するには  
  
1. ホーム ロールがイニシエーターが 3A4 アグリーメントを作成します。 ホーム組織の GBI を 123456789 に設定し、GBI を 987654321 にパートナーを設定します。 これにより、SDK の LOBApplication フォルダー下の SampleInstances フォルダーにサンプルを使用できます。  
  
2. Loopback アグリーメント ミラー ユーティリティを使用して、手順 1. で作成した 3A4 PIP のミラーを作成します。  
  
3. LOBApplication.exe SDK ユーティリティを使用して、3A4 PIP 要求メッセージを送信します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK にはフォルダーに入力のサンプルが含まれています\<*インストール ディレクトリ*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml します。  
  
4. BTARNDATA データベースでは、次のクエリを実行します。  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. 数秒後は、このテーブルに 4 つの新しいメッセージが表示されます。 そのうち 2 つは、受信確認シグナルです。 1 つのシグナルは Async 3A4 要求メッセージです。 1 つのシグナルは Async 3A4 応答メッセージです。  
  
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を再度実行する前に Cleanup.bat を実行する必要があります。  
  
## <a name="remarks"></a>コメント  
 パブリック オーケストレーションでは、受信確認 (ACK および NACK シグナル メッセージ) が自動的に生成されます。 基幹業務 (LOB) アプリケーションは、それらを生成する必要はありません。  
  
 MessagesFromLOB テーブルにルーティングされるメッセージの形式を lobmessage と呼びます。 スキーマは、C:\Program files \microsoft BizTalk Accelerator RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd for で使用できます。 使用する場合、`RNIFSubmit`メソッドがありません、メッセージの形式を使用します。 のみ、ServiceContent に追加情報を送信する必要があります。 `RNIFSubmit` MessagesFromLOB テーブルにレコードが生成されます。  
  
## <a name="filtering-out-single-action-messages"></a>シングル アクション メッセージをフィルター処理  
 このオーケストレーションはダブル アクション メッセージのみを受信する必要があります。 シングル アクション Pip をサポートするには、このサンプル プロジェクトを拡張する必要がありません。 このオーケストレーションを使用して、シングル アクション メッセージを処理する場合は、BTARN によってエラーが通知されます。 シングル アクション メッセージの受信からオーケストレーションを防ぐためには、PIPAutomationGetAction ストアド プロシージャに次の行を変更します。  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 上記の行には、シングル アクション メッセージをフィルター処理する WHERE 句を追加します。 すべてのシングル アクション メッセージ処理するには WHERE 句が含まれます。 行は、次のようにする必要があります。  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a>参照  
 [3 a 2 要求を 3 a 2 応答のマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)   
 [3A4 要求から 3A4 応答のマップ サンプルへ](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)