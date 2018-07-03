---
title: '手順 11: AS2 ソリューションのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 184ed8ee-6778-4bb9-b265-a94a1fed03cb
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31fbb336d4fb6ba7184a7745520603923c67ce4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996243"
---
# <a name="step-11-test-the-as2-solution"></a>手順 11: AS2 ソリューションをテストします。
![手順 11 の 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")  
  
 このステップでは、このチュートリアルの結果を確認します。  
  
 EDI メッセージを受信場所の Receive_AS2 に (Contoso 仮想ディレクトリを介して) 送信するために使用する Sender.exe ファイルを構築する必要があります。 Sender.exe は、非同期の MDN メッセージを返します。 メッセージ ファイルは X12_00401_864.edi であり、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial フォルダーにあります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-test-the-solution-with-an-asynchronous-edi-message"></a>EDI メッセージが非同期ソリューションをテストするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。 Sender プロジェクトを右クリックし、**プロパティ**します。 クリックして**署名**左側のコンソールでします。 いることを確認**アセンブリに署名**選択すると、および厳密な名前キー ファイルに設定が**Sender.snk**します。 必ず**遅延署名のみ**がクリアされます。  
  
2. プロジェクトをビルドする。  
  
3. コマンド プロンプトを開き、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug に移動します。 Enter `Sender.exe`、押します **」と入力**します。 AS2 メッセージが正常に送信されたことを示すメッセージを確認し、コマンド プロンプトを閉じます。  
  
   > [!NOTE]
   >  Sender.exe ビルドを次を含む AS2 メッセージが実行されている EDI テスト インターチェンジ: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \x12_00401_864.edi します。 AS2 メッセージのビルド後、そのメッセージは Contoso 仮想ディレクトリに送られます。このディレクトリは、BTSHttpReceive.dll を使用してメッセージを受信場所にルーティングします。  
  
4. 移動し、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_MDNToFabrikam フォルダー。 あることを確認、 \<GUID\>フォルダー内に <guid>.msg ファイル。 メモ帳でこのファイルを開き、メッセージが MDN で、AS2-From が Contoso に設定され、AS2-To が Fabrikam に設定されていることを確認します。  
  
5. 移動し、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso フォルダー。 あることを確認、 \<GUID\>フォルダーの .xml ファイルです。 このファイルをダブルクリックし、メッセージの ST01 フィールドが 864 に設定されていることを確認します。  
  
6. 移動し、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_ 997tofabrikam フォルダー。 あることを確認、 \<GUID\>フォルダー内に <guid>.msg ファイル。 メモ帳でこのファイルを開き、メッセージが、EDI ペイロードの上に AS2 ヘッダーがある 997 メッセージ (ST1 が 997) であることを確認します。 AS2-From が Contoso で、AS2-To が Fabrikam であることを確認します。 ISA6 (送信者 ID) が 1234567 (Contoso) に設定されていること、および ISA8 (受信者 ID) が 7654321 (Fabrikam) に設定されていることを確認します。  
  
7. AS2 および EDI 状態レポートを表示するには、**グループ ハブ**BizTalk Server 管理コンソールでページで、ページの一番下までスクロールし、状態レポートのリンクをクリックします。 詳細については、次を参照してください。 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)します。  
  
## <a name="next-steps"></a>次の手順  
 これで、AS2 のチュートリアルを終了します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)   
 [手順 1: AS2 チュートリアルの準備](../core/step-1-prepare-for-the-as2-tutorial.md)