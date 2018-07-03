---
title: AS2 送信者ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e2a88fc-67fd-4801-a6f8-1e7c92098eaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b07b2d791f4870b608e552189cd2f35754c950
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998219"
---
# <a name="as2-sender-utility"></a>AS2 送信者ユーティリティ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の AS2 送信者ユーティリティを使用すると、1 台のコンピューターで Web サイトに AS2 メッセージを送信できます。 このユーティリティは、個別のコンピュータからの AS2 メッセージの送信をシミュレートします。  
  
 AS2 送信者ユーティリティ ファイルは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender にあります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
## <a name="what-this-utility-does"></a>このユーティリティの処理  
 AS2 送信者ユーティリティは EDI ペイロードを含む AS2 メッセージを作成し、BTSHTTPReceive ISAPI フィルタを使用する Web サイトにそのメッセージを送信します。 既定では、チュートリアルは次の処理を実行します。  
  
- 864 X12 エンコード ペイロードを含む X12_00401_864.edi という名前の AS2 メッセージを送信します。 このメッセージは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial フォルダーにあります。  
  
- AS2 メッセージへの応答として非同期 MDN を表示します。 これは送信されたメッセージによって決まり、変更できます。  
  
- Contoso 仮想ディレクトリ経由で受信場所に AS2 メッセージを送信します。  
  
  この特定の動作を変更するようにこのユーティリティを変更できます。 参照してください、 [AS2 送信者ユーティリティをカスタマイズする方法](../core/as2-sender-utility.md#BKMK_Custom)以下のセクション。  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a>AS2 送信者ユーティリティを使用してソリューションを設定する方法  
 AS2 送信者ユーティリティを使用するソリューションを設定するには、次の手順を行う必要があります。  
  
> [!IMPORTANT]
>  これらの手順は、AS2 チュートリアルおよび送信側の AS2 の 2 つのチュートリアルで例示されています。 詳細については、次を参照してください[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)、[チュートリアル (AS2): 同期 MDN による AS2 経由で送信する EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)、および[チュートリアル (AS2):、非同期による AS2 経由での EDI の送信。MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)します。  
  
-   BTSHTTPReceive ISAPI フィルタを有効にします。  
  
-   AS2 メッセージを受信するように Web ページおよび受信場所を構成します。 既定の AS2 送信者ユーティリティでは、Web ページは Contoso Web ページです。  
  
-   AS2 メッセージのペイロードとして送信する EDI インターチェンジのスキーマを展開します。  
  
-   適切な AS2 および EDI パーティ プロパティを設定します。  
  
##  <a name="BKMK_Custom"></a> AS2 送信者ユーティリティをカスタマイズする方法  
 既定では、AS2 送信者ユーティリティは、BTSHTTPReceive ISAPI フィルタを使用して、テスト 864 EDI インターチェンジを AS2 経由で Contoso Web ページに送信します。 X12_00401_864.edi という名前の AS2 メッセージは、非同期 MDN を表示します。 AS2 送信者ユーティリティ コードは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender フォルダーの HttpSender.cs にあります。 既定の 864 テスト ファイルを送信する HttpSender.cs 内のコード行を次に示します。  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  別のファイル名と別のパスを使用してこの行を変更できます。  
  
 HttpSender.cs 内の次の行は、X12_00401_864-Sync.edi という名前の AS2 メッセージを送信します。 このメッセージは同期 MDN を表示します。 既定では、HttpSender.cs 内のこのコード行は、X12_00401_864.edi を送信する行を優先してコメント アウトされています。 X12_00401_864-Sync.edi を送信するには、X12_00401_864-Sync.edi 行のコメント化を解除し、X12_00401_864.edi 行をコメント化します。  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 HttpSender.cs 内の次のコード行は、Contoso Web ページにメッセージを送信します。  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  別の仮想ディレクトリと ISAPI フィルタを使用してこの行を変更できます。  
  
### <a name="to-build-the-as2-sender-sample"></a>AS2 送信者のサンプルをビルドするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。  
  
2. Sender プロジェクトの HttpSender.cs を開き、適切な受信 Web ページおよび EDI ファイル名とパスを使用して送信者コードをカスタマイズします。  
  
3. Sender プロジェクトを右クリックし、**プロパティ**します。  
  
4. クリックして**署名**左側のコンソールでします。 いることを確認**アセンブリに署名**が選択されている厳密な名前キー ファイルに設定されていると**Sender.snk**します。 必ず**遅延署名のみ**がクリアされます。  
  
5. プロジェクトをビルドする。  
  
### <a name="to-run-the-as2-sender-sample"></a>AS2 送信者のサンプルを実行するには  
  
1. コマンド プロンプトを開きます。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug に移動します。  
  
2. Enter **Sender.exe**、押します **」と入力**します。  
  
3. AS2 メッセージが正常に送信されたことを示すメッセージを確認し、コマンド プロンプトを閉じます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)   
 [チュートリアル (AS2): 同期 MDN による AS2 経由で EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)   
 [チュートリアル (AS2): 非同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)