---
title: "Siebel するポートのバインド ファイルを使用する物理ポートのバインドの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring by using a port binding file
ms.assetid: 1758e89c-d56c-4e67-919b-c0bbb22878bf
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05bfa8539c223078fd29c5d99cfac50217bbaa36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-siebel"></a>Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマ ファイルは、以外の Siebel 成果物を表すメタデータを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]もポートのバインド ファイルを生成します。 物理送信ポートを作成する BizTalk アプリケーションにこのバインド ファイルをインポートすることができます。 参照してください[Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)です。 このバインド ファイルをインポートする場合がありませんを物理送信ポートを手動で作成します。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]文字列型のバインド プロパティの値を指定しないと、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインディングのプロパティとその値、バインド ファイルに必要な場合です。  
  
 ポートのバインド ファイルを常に使用するポートを作成するには、双方向の送信ポートが作成されます。 一方向のポートを作成する場合は、ことができます、手動で作成する次の手順に従って、 [Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。 または、一方向のポートを作成するポートのバインド ファイルを変更するには、このトピックに記載されている回避策を実行することができます。  
  
> [!IMPORTANT]
>  使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] Wcf-siebel ポートを作成することができますを使用してポートのバインド ファイルは作成されません。 ただし、行うことができるいくつかの変更によって生成されたポートのバインド ファイル、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Wcf-siebel ポートの作成に使用します。 詳細については、WCF Siebel ポートを使用して、ポートのバインド ファイルが生成を使用して アダプター サービスのアドインの構成を参照してください。  
  
 によって生成されたバインド ファイルに関して理解しておく必要があります重要な点は次のとおり、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   ファイルは、特定の名前付け規則で作成されます。 Siebel システムへのメッセージを送信するには、送信操作は、のメタデータを生成した場合は、WcfSendPort_SiebelBinding_Custom.bindinginfo.xml は、ファイルの名前です。  
  
-   ファイルには、バインド構成、バインドの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づくポート操作に関する情報が含まれています。 ポートを作成するには、このバインド ファイルをインポートするときに、ポートの物理ポートを構成するために必要なすべての関連情報が自動的に設定します。  
  
    > [!IMPORTANT]
    >  既定では、送信ポートのアクションは、メタデータを生成する操作名にマップされます。 たとえば、アカウント ビジネス コンポーネントに対する挿入操作のメタデータを生成する場合、ポートでアクションに設定が`<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />`です。 ただし、BizTalk オーケストレーションで作成する論理送信ポートで、操作名はありません、同じです。 (BizTalk オーケストレーション) の論理ポートと物理送信ポート (BizTalk Server 管理コンソール) にある操作名が同じであることを確認する必要があります。 それ以外の場合は、送信ポート経由で Siebel システムにメッセージを送信中にエラーが表示されます。  
  
-   のみ、Siebel システムへの接続にポートの資格情報を提供する必要があります。 バインド ファイルには、接続に使用するユーザー名を保持は、セキュリティ上の理由、バインド ファイルはパスワードです。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
-   バインド ファイルをインポートするときに、ダイアログ メッセージ通知する、バインド ファイル内の BizTalk アプリケーション名では、バインド ファイルをインポートするアプリケーション名が一致しないことを取得する可能性があります。 安全にこのメッセージは無視して続行できます。  
  
-   バインド ファイルは、受信場所もにポートの名前を格納および構成。 バインド ファイルをインポートする BizTalk アプリケーションは、ポート、または、同じ BizTalk アプリケーションで既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが表示されます。 ポートに一意の名前を指定するか、受信場所にバインド ファイルを手動で編集する必要があります。  
  
-   既定では、ポートのバインド ファイルには、双方向の送信ポートの定義が常に含まれます。 BizTalk アプリケーションでこのファイルをインポートするときに、双方向の送信ポートを作成します。 ただし、一方向の送信ポートを持つオーケストレーションがあります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートがリストに表示できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーションで作成した物理ポートは双方向のポートのために発生します。 このような場合は、次の変更を加えるバインド ファイルを編集できます。  
  
    |こちらは|方法|  
    |--------------|-------------|  
    |構成するポートのバインド ファイルを編集するための一方向送信ポート|値を変更するのには次の抜粋では、 **IsTwoWay**プロパティを**false**です。 最初に、この設定は**true**です。<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -次の抜粋をコメント化します。<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-siebel-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>使用して生成されたポートのバインド ファイルを使用して WCF Siebel ポートを構成するアダプターを使用する追加のサービス  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]でインポートできるポートのバインド ファイルも作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ポートを作成する、BizTalk WCF Siebel で同じポートのバインド ファイルを使用することができます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ただし、Wcf-siebel ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1.  テキスト エディターで、ポートのバインド ファイルを開きます。  
  
2.  検索して置き換えます名を使用するには、Wcf-siebel アダプターが追加されます。"Wcf-custom"[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 たとえば、"SiebelAdapter"として Wcf-siebel アダプターを追加した場合は、"SiebelAdapter"と"Wcf-custom"を置き換えます。  
  
3.  "ConfigurationClsid"属性を検索し、既存の属性の値を"7971A78D-AE8F-42B4-834D-3A957FD945E9"に置き換えます。  
  
4.  保存して、バインド ファイルを閉じます。  
  
5.  バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 参照してください[Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)です。 
  
## <a name="see-also"></a>参照  
[ビルド ブロック、Siebel を BizTalk アプリケーションを作成するには 

アダプター] (../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)