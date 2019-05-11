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
ms.openlocfilehash: 37a6c7ea0500b24db9a99d94ea4044a0d645b134
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358857"
---
# <a name="as2-sender-utility"></a>AS2 送信者ユーティリティ
AS2 送信者ユーティリティが付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 台のコンピューター上の Web サイトに AS2 メッセージを送信することができます。 このユーティリティは、個別のコンピュータからの AS2 メッセージの送信をシミュレートします。  
  
 AS2 送信者ユーティリティ ファイルにある[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 tutorial \sender します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
## <a name="what-this-utility-does"></a>このユーティリティの処理  
 AS2 送信者ユーティリティは、EDI ペイロードを持つ AS2 メッセージを構築し、BTSHTTPReceive ISAPI フィルタを使用する Web サイトにそのメッセージを送信します。 既定では、このチュートリアルは、次でください。  
  
- 864 X12 エンコードのペイロードを含む X12_00401_864.edi という名前の AS2 メッセージを送信します。 このメッセージにある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial フォルダー。  
  
- AS2 メッセージへの応答として非同期 MDN メッセージが表示されます。 これは、送信されるメッセージによって決定され、変更することができます。  
  
- Contoso 仮想ディレクトリ経由で受信場所には、AS2 メッセージを送信します。  
  
  ユーティリティは、この特定の動作を変更するのには変更できます。 参照してください、 [AS2 送信者ユーティリティをカスタマイズする方法](../core/as2-sender-utility.md#BKMK_Custom)以下のセクション。  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a>AS2 送信者ユーティリティを使用してソリューションを設定する方法  
 AS2 送信者ユーティリティを使用して、ソリューションを設定するには、次の操作をする必要があります。  
  
> [!IMPORTANT]
>  AS2 チュートリアルおよび AS2 送信側の 2 つのチュートリアルでは、次の手順が示されています。 詳細については、次を参照してください。[チュートリアル 3。AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)、[チュートリアル (AS2)。同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)、および[チュートリアル (AS2)。非同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)します。  
  
-   BTSHTTPReceive ISAPI フィルタを有効にします。  
  
-   Web ページと AS2 メッセージを受信する受信場所を構成します。 既定の AS2 送信者ユーティリティでは、Web ページは、Contoso Web ページです。  
  
-   AS2 メッセージのペイロードとして送信する EDI インターチェンジのスキーマをデプロイします。  
  
-   適切な AS2 および EDI パーティ プロパティを設定します。  
  
##  <a name="BKMK_Custom"></a> AS2 送信者ユーティリティをカスタマイズする方法  
 既定の AS2 送信者ユーティリティは、テスト 864 EDI インターチェンジを AS2 経由で、BTSHTTPReceive ISAPI フィルタを使用して Contoso Web ページに送信します。 X12_00401_864.edi という名前の AS2 メッセージには、非同期 MDN メッセージが表示されます。 AS2 送信者ユーティリティ コードは、HttpSender.cs 内にある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 \sender フォルダー。 HttpSender.cs 内のコードは、次の行では、既定の 864 テスト ファイルを送信します。  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  別のファイル名と異なるパスを使用してこの行を変更することができます。  
  
 HttpSender.cs 内の次の行では、x12_00401_864-sync.edi という名前の AS2 メッセージを送信します。 このメッセージは、同期 MDN を表示します。 既定では、HttpSender.cs 内のコード行がコメント アウトされて X12_00401_864.edi を送信する行を優先します。 X12_00401_864-sync.edi を送信するには、X12_00401_864.edi 行をコメント アウト、x12_00401_864-sync.edi 行をコメント解除します。  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 HttpSender.cs 内のコードは、次の行では、Contoso Web ページにメッセージを送信します。  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  別の仮想ディレクトリと ISAPI フィルターを使用してこの行を変更することができます。  
  
### <a name="to-build-the-as2-sender-sample"></a>AS2 送信者のサンプルをビルドするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。  
  
2. Sender プロジェクトでは、HttpSender.cs を開き、適切な受信側の Web ページと、適切な EDI ファイル名とパスを使用して送信者コードをカスタマイズします。  
  
3. Sender プロジェクトを右クリックし、**プロパティ**します。  
  
4. クリックして**署名**左側のコンソールでします。 いることを確認**アセンブリに署名**が選択されている厳密な名前キー ファイルに設定されていると**Sender.snk**します。 必ず**遅延署名のみ**がクリアされます。  
  
5. プロジェクトをビルドする。  
  
### <a name="to-run-the-as2-sender-sample"></a>AS2 送信者のサンプルを実行するには  
  
1. コマンド プロンプトを開きます。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug に移動します。  
  
2. Enter **Sender.exe**、押します **」と入力**します。  
  
3. AS2 メッセージが正常に送信されたことを示すメッセージを確認し、コマンド プロンプトを閉じます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)   
 [チュートリアル (AS2):同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)   
 [チュートリアル (AS2):非同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)