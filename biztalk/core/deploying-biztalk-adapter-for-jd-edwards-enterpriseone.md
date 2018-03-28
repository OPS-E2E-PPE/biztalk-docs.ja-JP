---
title: JD Edwards EnterpriseOne のアプリケーションのインポート |Microsoft ドキュメント
description: セットアップの確認、アプリケーション バインド ファイルをインポートおよび BizTalk で JD Edwards EnterpriseOne アダプターの制限を確認します。
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55374c87192c993e26cc11cb496d89074d527868
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>JD Edwards EnterpriseOne アプリケーションをインポートします。
  
## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとターゲット コンピューター上のアセンブリを複製することができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、次のタスクを実行できます。  
  
-   BizTalk 構成データベース内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除する  
  
-   グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする  
  
使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。  
  
> [!NOTE]
>  Microsoft BizTalk Adapter for JD Edwards EnterpriseOne の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。 実稼動コンピュータでは Visual Studio は必要ありません。  

## <a name="confirm-your-setup"></a>セットアップを確認します。
BizTalk Server を使用してバインド ファイルをインポートする前に、以下の項目について確認する必要があります。  
  
-   CLASSPATH が JD Edwards EnterpriseOne 固有のファイルの特定の場所を指している。 新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。  
  
-   JD Edwards EnterpriseOne システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 詳細については、次を参照してください。**制限**」を参照します。

## <a name="clean-the-target-computer"></a>ターゲット コンピューターをクリーニングします。
バインド ファイルとアセンブリを展開先のコンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
インポートすると、前に、送信ポートを削除し、受信場所、オーケストレーションにバインドします。 Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  

たとえば、コマンド プロンプトで、次のコマンドを実行します。  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a>制限事項
によってエクスポートされるバインド ファイル (*) の星トランスポート アダプターのパスワードが格納されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、され、同じ形式で管理コンポーネントに渡されます。 アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次に、ファイルを使用してバインド情報をインポートするときはトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。  
  
 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  
### <a name="work-around-the-password-limitation"></a>パスワードの制限を回避するには  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。 SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  


## <a name="next-steps"></a>次の手順
[BizTalk Server 例外処理を使用して、オーケストレーションで](../core/using-biztalk-server-exception-handling3.md)