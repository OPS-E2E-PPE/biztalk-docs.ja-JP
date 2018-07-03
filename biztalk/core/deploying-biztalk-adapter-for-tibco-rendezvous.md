---
title: TIBCO Rendezvous のバインドのインポート |Microsoft Docs
description: BizTalk Server の バインドのインポート機能を使用して TIBCO Rendezvous アプリケーション用 BizTalk アダプターの展開します。
ms.custom: ''
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb362afb23b165c31df34adf521be81f93a621f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994011"
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a>TIBCO Rendezvous ポートとアセンブリを展開します。
  
## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。 ウィザードにより、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。  
  
 BizTalk Server を使用すると、次の操作を実行できます。  
  
- BizTalk 構成データベース内での、BizTalk Server アセンブリの展開または削除  
  
- グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール  
  
- バインド ファイルに対する、BizTalk Server アセンブリのバインド情報のインポートまたはエクスポート  
  
  使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)します。  
  
> [!NOTE]
>  Microsoft BizTalk Adapter for TIBCO Rendezvous の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。 実稼動コンピュータでは Visual Studio は必要ありません。  

## <a name="confirm-your-setup"></a>設定を確認します。

使用する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバインド ファイルをインポートするには、確認応答用のフォルダーが存在し、新しいコンピューター上と同じですか、バインド ファイルを編集する必要があります。  
  
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
  
## <a name="next-steps"></a>次のステップ
[BizTalk Server 例外処理を使用して、オーケストレーションで](../core/using-biztalk-server-exception-handling4.md)  
[[トラブルシューティング]](../core/troubleshooting-tibco-rendezvous.md)