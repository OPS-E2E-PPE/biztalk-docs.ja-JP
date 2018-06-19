---
title: Oracle E-business Suite へのポートのバインド ファイルを使用して物理ポートのバインドの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c3c468e-815c-4611-879c-8da9111eeb3b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6f582733b6ff545e96c671d7c98f58c211e6ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218266"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-e-business-suite"></a>Oracle E-business Suite へのポートのバインド ファイルを使用して物理ポートのバインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマ ファイルは、以外の Oracle E-business Suite の成果物のためのメタデータを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]もポートのバインド ファイルを生成します。 作成する物理送信ポートまたは受信ポートを BizTalk アプリケーションにこのバインド ファイルをインポートすることができます。 バインド ファイルをインポートする方法の詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。 このバインド ファイルをインポートする場合、手動で作成する物理送信ポートまたは受信ポートをするはありません。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]文字列型のバインド プロパティの値を指定しないと、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインディングのプロパティとその値、バインド ファイルに必要な場合です。  
  
 双方向の送信ポートを作成するポートのバインド ファイルを常に使用するポートを作成するか、一方向の受信ポート。 一方向の送信ポートを作成する場合は、ことができます、手動で作成する次の手順で説明した[Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。 または、一方向の送信ポートを作成するポートのバインド ファイルを変更するには、このトピックに記載されている回避策を実行することができます。  
  
> [!NOTE]
>  バインド ファイル、ポート、受信操作が常に作成の一方向の受信ポート。 これは、ため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サポートの一方向受信ポートの受信操作のみです。  
  
> [!IMPORTANT]
>  使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] Wcf-oracleebs ポートを作成することができますを使用してポートのバインド ファイルは作成されません。 ただし、行うことができるいくつかの変更によって生成されたポートのバインド ファイル、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Wcf-oracleebs ポートの作成に使用します。 詳細については、次を参照してください。 [Wcf-oracleebs ポートを使用して、ポートのバインド ファイルが生成を使用して アダプター サービスの追加で構成する](#BKMK_ModifyBinding)です。  
  
 ファイルをバインディングに関して理解していることの重要な点は次のとおり、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]が生成されます。  
  
-   ファイルは、特定の名前付け規則で作成されます。 送信操作のメタデータを生成した場合は、Oracle E-business Suite にメッセージを送信するファイルの名前は WcfSendPort_OracleEBSBinding_Custom.bindinginfo.xml です。  
  
     受信操作のメタデータを生成した場合は、Oracle E-business Suite からメッセージを受信するファイルの名前は WcfReceivePort_OracleEBSBinding_Custom.bindinginfo.xml です。  
  
-   ファイルには、バインド構成、バインドの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づくポート操作に関する情報が含まれています。 ポートを作成する BizTalk アプリケーションにこのバインド ファイルをインポートするときに、ポートで物理ポートを構成するために必要なすべての関連情報が自動的に設定します。  
  
    > [!IMPORTANT]
    >  既定では、送信ポートのアクションは、メタデータの生成対象の操作名にマップされます。 たとえば、インターフェイス テーブル (例: FA_BOOKS) に対する挿入操作のメタデータを生成する場合、ポートでアクションに設定が`<Operation Name="Insert" Action="InterfaceTables/Insert/OFA/FA/FA_BOOKS" />`です。 ただし、BizTalk オーケストレーションで作成する論理送信ポートで、操作名はありません、同じです。 論理操作名 (、BizTalk オーケストレーションで) ポートの送信および物理送信ポートのことを確認する必要があります (で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール) は、同じです。 それ以外の場合は、送信ポートから Oracle E-business Suite へのメッセージを送信中にエラーが表示されます。  
  
-   のみ、Oracle E-business Suite に接続するポートの資格情報を提供する必要があります。 バインド ファイルでは、接続に使用する、セキュリティ上の理由から、バインド ファイルは、パスワード、ユーザー名を保持します。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
-   バインド ファイルをインポートするときに、ダイアログ メッセージ通知する、バインド ファイル内の BizTalk アプリケーション名では、バインド ファイルをインポートするアプリケーション名が一致しないことを取得する可能性があります。 安全にこのメッセージは無視して続行できます。  
  
-   バインド ファイルは、受信場所もにポートの名前を格納および構成。 バインド ファイルをインポートする BizTalk アプリケーションは、ポート、または、同じ BizTalk アプリケーションで既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが表示されます。 ポートに一意の名前を指定するか、受信場所のバインド ファイルを手動で編集する必要があります。  
  
-   バインド ファイルには、接続 URI に関する情報も含まれています。 バインド ファイルを同じ BizTalk アプリケーション内の既存の受信場所として同じ受信 URI を持つ受信場所を作成する場合は、エラーが表示されます。 一意の URI を指定するバインド ファイルを手動で編集する必要があります。  
  
-   既定では、送信操作用のポートのバインド ファイルには、双方向の送信ポートの定義が常に含まれます。 BizTalk アプリケーションでこのファイルをインポートするときに、双方向の送信ポートを作成します。 ただし、一方向の送信ポートを持つオーケストレーションがあります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートがリストに表示できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーションで作成した物理ポートは双方向のポートのために発生します。 このような場合は、次の変更を行う、バインド ファイルを編集できます。  
  
    |こちらは|方法|  
    |--------------|-------------|  
    |構成するポートのバインド ファイルを編集するための一方向送信ポート|1.次の例の値を変更、 **IsTwoWay**プロパティを**false**です。 最初に、この設定は**true**です。<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false " BindingOption="0">`<br />2.次の抜粋をコメント化します。<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"   FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,   Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,   PublicKeyToken= token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
  
    > [!IMPORTANT]
    >  バインド ファイル、ポート、受信操作が常に作成の一方向の受信ポート。 これは、ため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サポートの一方向受信ポートの受信操作のみです。  
  
##  <a name="BKMK_ModifyBinding"></a>使用して生成されたポートのバインド ファイルを使用して Wcf-oracleebs ポートを構成するアダプターを使用する追加のサービス  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]でインポートできるポートのバインド ファイルを作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ポートを作成する、BizTalk Wcf-oracleebs で同じポートのバインド ファイルを使用することができます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ただし、Wcf-oracleebs ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1.  テキスト エディターで、ポートのバインド ファイルを開きます。  
  
2.  検索して置き換えます名を使用するで Wcf-oracleebs アダプターが追加されます。"Wcf-custom"[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 たとえば、"OracleEBSAdapter"として Wcf-oracleebs アダプターを追加した場合は、"OracleEBSAdapter"と"Wcf-custom"を置き換えます。  
  
3.  "ConfigurationClsid"属性を検索し、既存の属性の値を"F452BB15-7A0D-495d-9395-C630D3FD29CD"に置き換えます。  
  
4.  保存して、バインド ファイルを閉じます。  
  
5.  バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 バインド ファイルをインポートする方法については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)