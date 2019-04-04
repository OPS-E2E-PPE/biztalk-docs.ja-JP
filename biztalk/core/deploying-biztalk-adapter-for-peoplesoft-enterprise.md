---
title: PeopleSoft アプリケーションのインポート |Microsoft Docs
description: XML バインド ファイルを使用して、BizTalk Server に、PeopleSoft アダプターのアプリケーションをインポートして、インポートするときに、制限事項を読み取る
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f53d1b4-e1df-41ff-b554-1bb1d20b9111
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f92775382a0d1af22d1bc7ef2c08f19305e90c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753202"
---
# <a name="deploy-biztalk-adapter-for-peoplesoft-enterprise"></a>BizTalk Adapter for PeopleSoft Enterprise を展開します。
ここでは、BizTalk Adapter for PeopleSoft Enterprise の展開に関する情報を示します。  

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。  
  
 使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのタスクを実行します。  
  
- BizTalk 構成データベースで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除します。  
  
- グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール  
  
- バインド ファイルに対する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリのバインド情報のインポートまたはエクスポート  
  
使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)します。  
  
> [!NOTE]
>  Microsoft BizTalk Adapter for PeopleSoft Enterprise の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。 実稼動コンピュータでは Visual Studio は必要ありません。  

## <a name="confirm-your-setup"></a>設定を確認します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。  
  
-   CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。 新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。  
  
-   PeopleSoft Enterprise システム パスワードは、構成に存在する場合、として保存されます\* \* \* \* \*バインド ファイルにします。 参照してください**制限**このトピックの「します。

> [!NOTE]
>  展開すると、受信場所の構成が上書きされます。 バインド ファイルとアセンブリをターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
 バインド ファイルをインポートする方法の詳細な手順は、[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)を参照してください。 
  
## <a name="clean-the-target-computer"></a>ターゲット コンピューターをクリーニングします。
新しいアプリケーションをデプロイするためのターゲット コンピューターのクリーニング、送信ポートを削除する受信場所をオーケストレーションにバインドされます。  
  
Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs を送信します。**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信**  
  
たとえば、コマンド プロンプトで次のように実行します。  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>制限事項
アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) によってエクスポートされるバインド ファイルに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で管理コンポーネントに渡すと、同じ形式です。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が完了した後、バインド ファイルからパスワードを削除する必要があります。  
  

### <a name="work-around-the-password-limitation"></a>パスワードの制限を回避するには  

**オプション 1**   
  
- インポートする前に、アスタリスクをプレーン テキストに置き換えることにより、バインド ファイルを更新します。  
  
  > [!CAUTION]
  >  この操作は、セキュリティ上の理由により推奨されていません。  
  
- インポートする前に、無効な値 (つまり、正しくないパスワード)、アスタリスクを置き換えてバインド fileby を更新します。 インポートした後、正しいパスワードを入力、**トランスポートのプロパティ**BizTalk Server 管理コンソール。  
  
  > [!NOTE]
  >  この対処方法を使用できるのは、ターゲット コンピューターに Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされているか、カスタム ツールを開発する場合のみです。  
  
**オプション 2**  
  
-   パスワードではなく、エンタープライズ シングル サインオン (SSO) を使用します。 SSO オプションを使用するには、バインド ファイルをインポートする必要があります。  
  
- 論理システムと送信を確認し、サービスを受信します。 
  
## <a name="next-steps"></a>次の手順
[BizTalk Server 例外処理を使用して、オーケストレーションで](../core/using-biztalk-server-exception-handling2.md)