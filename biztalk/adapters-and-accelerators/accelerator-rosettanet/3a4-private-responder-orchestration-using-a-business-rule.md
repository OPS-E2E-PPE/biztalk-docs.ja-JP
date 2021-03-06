---
title: ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33d87952-def6-4202-b535-3d80171332eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6af8d06ddda2019982bd3ba83bf5d638208c2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285033"
---
# <a name="3a4-private-responder-orchestration-using-a-business-rule"></a>ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション
PIP3A4PrivateResponder.odx サンプルは、ビジネス ルールを組み込んでいる PIP (Partner Interface Process) 固有の応答側プライベート プロセスの実装方法を示した、プライベート プロセス オーケストレーションです。 このプロセスの詳細については、次を参照してください。[プライベート プロセス オーケストレーションのビジネス ルールを定義する](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md)します。  
  
 既定では、Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップ プログラムによってサンプルでは、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet\SDK\PipAutomation\3A4 します。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド プロンプトで、 *\<ドライブ\>*: Microsoft BizTalk Accelerator for RosettaNet \Program Files\\<バージョン\>\SDK\PIPAutomation\3A4 フォルダー。  
  
2.  ファイル Setup.bat を実行します。このファイルによって、Binding.xml バインド ファイルを使用して次のアクションが実行されます。  
  
    -   Helper プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
    -   PIP3APrivateResponder プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
    -   LOB_To_PrivateResponder 受信ポートを作成します。  
  
    -   LOB_To_PrivateResponder 受信場所を作成します。  
  
    -   PrivateResponder_To_LOB 送信ポートを作成し、開始します。  
  
    -   PIP3A4PrivateResponderProcess オーケストレーションをコンパイルし、展開します。  
  
    > [!NOTE]
    >  BizTalk エクスプローラを使用して、PIP3A4PrivateResponderProcess オーケストレーションのポート バインド構成を完成する必要があります。  
  
    > [!NOTE]
    >  setup.bat による変更を元に戻すには、手動で PIP3A4PrivateResponder.odx オーケストレーションの登録を解除し、Helper および PIP3A4PrivateResponder のアセンブリの展開を解除し、samplebtarnpolicy ルールのポリシーの展開を解除して削除します。 Cleanup.bat を使用することはできません、 *\<ドライブ\>*: Microsoft BizTalk Accelerator for RosettaNet \Program Files\\<バージョン\>\SDK\PIPAutomation\3A4 フォルダーの変更を元に戻すsetup.bat によって行われます。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、3A4 要求アクションとシグナル メッセージをサブスクライブし、 3A4 の同期処理と非同期処理のどちらでも使用できます。 これ以外の PIP メッセージは、すべて汎用の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] プライベート プロセスを引き続き使用してルーティングします。 このサンプルにより、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール エンジンが呼び出され、着信 3A4 要求メッセージがルール エンジンに渡されます。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ある samplebtarnpolicy.xml という名前のサンプルのビジネス ルール ポリシーが提供されます\<*ドライブ*\>: Microsoft BizTalk Accelerator for RosettaNet \Program Files\\<バージョン\>\SDK\PipAutomation\3A4 します。 詳細については、次を参照してください。[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)します。  
  
 このサンプルを使用するには、ビジネス ルールを設定する必要があります。 メッセージがビジネス ルールに適合すると、受信アクション メッセージが MessagesToLOB テーブルに保存され、Delivered Status が 2 に設定されます。 この要求の確認を生成する必要がないことを基幹業務アプリケーションが認識できるように、[Delivered] 列の値はゼロ以外である必要があります。 次に、3A4 要求メッセージが 3A4 確認メッセージにマップされ、`SubmitRNIF` メソッドを使用して応答が MessageStorageIn テーブルに送信されます。  
  
 メッセージがビジネス ルールに適合しない場合、受信アクション メッセージは MessageStorageOut テーブルに保存され、Delivered Status は 0 に設定されます。  
  
 このサンプルには、PIP3A4PrivateResponder.odx のオーケストレーションで使用する送信ポート (PrivateResponder_To_LOB)、受信ポート (LOB_To_PrivateResponder)、および受信場所 (LOB_To_PrivateResponder) を設定するためのバインド ファイル (Binding.xml) が含まれています。 これらのバインドを Binding.xml ファイルにインポートするには、BTSTask コマンドを使用します。 詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」のトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [ダブル アクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)   
 [サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)