---
title: BizTalk Adapter for JD Edwards OneWorld にインポート |Microsoft Docs
description: アプリケーションのバインド ファイルをインポートおよび BizTalk で JD Edwards OneWorld アダプターの制限事項を確認してください。
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca65c71e14d488b264d861616fe170220ac249b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999219"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>JD Edwards EnterpriseOne アプリケーションをインポートします。
  
## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。 BizTalk Server により、送信ポートおよび受信場所の構成が XML ファイルにインポートされます。  
  
 BizTalk Server を使用すると、次のタスクを実行します。  
  
-   BizTalk 構成データベース内の BizTalk Server アセンブリを展開または削除する  
  
-   グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする  
  
-   BizTalk Server アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする  

使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)します。  
  
> [!NOTE]
>  Microsoft BizTalk Adapter for JD Edwards OneWorld の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。 実稼動コンピュータでは Visual Studio は必要ありません。  

## <a name="confirm-your-setup"></a>設定を確認します。
BizTalk Server を使用してバインド ファイルをインポートする前に、次のことを確認します。  
  
-   CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。 新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。  
  
-   JD Edwards システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 参照してください**制限**このトピックの「します。

  
> [!NOTE]
>  展開には、受信場所の構成が上書きされます。 バインド ファイルとアセンブリを展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
  
## <a name="clean-the-target-computer"></a>ターゲット コンピューターをクリーニングします。
展開には、受信場所の構成が上書きされます。 バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
インポートする前に、送信ポートを削除して、受信場所をオーケストレーションにバインドされています。  
  
Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
たとえば、コマンド プロンプトで次のように実行します。  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a>制限事項
アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) の管理に渡される BizTalk 展開ウィザードによってエクスポートされるバインド ファイルに同じ形式でのコンポーネントです。 アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページ。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  
> [!NOTE]
>  .Msi ファイルをインポートするときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンタープライズ アダプターのいずれかのバインド情報を格納しているアプリケーションのインポート エラー メッセージが表示される可能性があります。 サポートされている修正プログラムがエラーの完全な説明と共に、Microsoft から入手できる[ http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us)します。  
  
### <a name="work-around-the-password-limitation"></a>パスワードの制限を回避するには  

**オプション 1**  

- インポートする前に、アスタリスクをプレーン テキストに置き換えることにより、バインド ファイルを更新します。  
  
    > [!CAUTION]
    >  これは、セキュリティ上の理由により推奨されていません。  
  
- インポートする前を無効な値 (つまり、正しくないパスワード)、アスタリスクを置き換えることで、バインド ファイルを更新します。 インポートした後を使用して、正しいパスワードを入力、**トランスポートのプロパティ**します。  
  
    > [!NOTE]
    >  この回避できる場合にのみ使用、ターゲット コンピューター上またはカスタム ツールを開発することで、Microsoft Visual Studio がインストールされています。  
  
**オプション 2**  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。 SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  

## <a name="next-steps"></a>次のステップ
[BizTalk Server 例外処理を使用して、オーケストレーションで](../core/using-biztalk-server-exception-handling1.md)