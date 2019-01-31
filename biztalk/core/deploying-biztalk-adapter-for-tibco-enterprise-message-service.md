---
title: TIBCO EMS のバインドのインポート |Microsoft Docs
description: BizTalk Server でバインドのインポート機能を使用して TIBCO Enterprise Message Service のアプリケーション用 BizTalk アダプターの展開します。
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90d083833e7961770c6ecd535e9ed3e5143be30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981363"
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a>TIBCO EMS のポートとアセンブリを展開します。

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとターゲット コンピューター上のアセンブリを複製することができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エクスポートは、ポートおよび受信場所の構成を XML ファイルに送信します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、次のタスクを実行できます。  
  
- BizTalk 構成データベースで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除します。  
  
- グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール  
  
- バインド ファイルに対する、BizTalk アセンブリのバインド情報のインポートまたはエクスポート  
  
  使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)します。  
  
> [!NOTE]
>  Microsoft BizTalk Adapter for TIBCO Enterprise Message Service の場合のみ、ソース (開発) コンピューターに Visual Studio がインストールされている必要があります。 実稼動コンピュータでは Visual Studio は必要ありません。  

## <a name="confirm-your-setup"></a>設定を確認します。
BizTalk Server を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。  
  
-   新しいコンピューターで、応答用のフォルダーが存在し、同じである。同じでない場合は、バインド ファイルを編集します。  
  
-   TIBCO Enterprise Message Service システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存される必要があります。 参照してください**制限**このトピックの「します。


## <a name="clean-the-target-computer"></a>ターゲット コンピューターをクリーニングします。
展開には、受信場所の構成が上書きされます。 バインド ファイル (およびアセンブリ) をターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  

をインポートする前に、送信ポートを削除し、受信場所、オーケストレーションにバインドします。  
  
Microsoft Visual Studio がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

たとえば、コマンド プロンプトで次のように実行します。  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>制限事項
トランスポート アダプターのパスワードは、星として格納されます (\*\*\*\*\*\*)、BizTalk Server によってエクスポートされるバインド ファイルにされ、同じ管理コンポーネントに渡されます形式です。 アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。  
  
 これは、既知の制限です。 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後は、バインド ファイルからパスワードを削除する必要があります。  
  
 
### <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 このパスワードの制限に対処するには、次のいずれかの方法を使用します。  
  
-   アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
    > [!CAUTION]
    >  これは、セキュリティ上の理由により推奨されていません。  
  
-   アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。  
  
    > [!NOTE]
    >  この対処方法を使用できるのは、ターゲット コンピューターに Visual Studio がインストールされているか、カスタム ツールを開発する場合のみです。  
  
-   論理システムと送信および受信サービスを確認します。  

## <a name="next-steps"></a>次のステップ
[BizTalk Server 例外処理を使用して、オーケストレーションで](../core/using-biztalk-server-exception-handling5.md)