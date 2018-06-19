---
title: SAP にポートのバインド ファイルを使用して物理ポートのバインドの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring using a port binding file
ms.assetid: c637971c-3ecd-4026-8f74-bd5173774438
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0383ad738140467f17e4ff56ba60f2cc5b9698f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217594"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-sap"></a>SAP にポートのバインド ファイルを使用して物理ポートのバインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマ ファイル以外、SAP アイテムのメタデータを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]もポートのバインド ファイルを生成します。 作成する物理送信ポートまたは受信ポートを BizTalk アプリケーションにこのバインド ファイルをインポートすることができます。 [SAP アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)バインド ファイルをインポートする手順が含まれています。 このバインド ファイルをインポートする場合、手動で作成する物理送信ポートまたは受信ポートをするはありません。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]文字列型のバインド プロパティの値を指定しないと、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインディングのプロパティとその値、バインド ファイルに必要な場合です。  
  
 ポートのバインド ファイルを常に使用するポートを作成する、双方向の送信を作成または、ポートを受信します。 一方向のポートを作成する場合は、ことができます、手動で作成する手順を使用して、 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。 または、一方向のポートを作成するポートのバインド ファイルを変更するには、このトピックに記載されている回避策を実行することができます。  
  
> [!IMPORTANT]
>  使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] WCF SAP ポートを作成することができますを使用してポートのバインド ファイルは作成されません。 ただし、行うことができるいくつかの変更によって生成されたポートのバインド ファイル、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] WCF SAP ポートを作成するとします。 詳細については、次を参照してください。[ポートのバインド ファイルが生成を使用して アダプター サービスのアドインを使用して WCF SAP ポートを構成する](#BKMK_add_wcf_sap)です。  
  
 によって生成されたバインド ファイルに関して理解しておく必要があります重要な点は次のとおり、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   ファイルは、特定の名前付け規則で作成されます。 を SAP システムにメッセージを送信するには、送信操作のメタデータを生成した場合は、WcfSendPort_SAPBinding_Custom.bindinginfo.xml は、ファイルの名前です。  
  
     を SAP システムからメッセージを受信するには、受信操作のメタデータを生成した場合は、WcfReceivePort_SAPBinding_Custom.bindinginfo.xml は、ファイルの名前です。  
  
-   ファイルには、バインド構成、バインドの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づくポート操作に関する情報が含まれています。 ポートを作成するには、このバインド ファイルをインポートするときに、ポートの物理ポートを構成するために必要なすべての関連情報が自動的に設定します。  
  
    > [!IMPORTANT]
    >  既定では、送信ポートのアクションは、メタデータを生成する操作名にマップされます。 たとえば、RFC_CUSTOMER_GET のメタデータを生成する場合、ポートでアクションに設定が`<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />`です。 ただし、BizTalk オーケストレーションで作成する論理送信ポートで、操作名はありません、同じです。 (BizTalk オーケストレーション) の論理ポートと物理送信ポート (BizTalk Server 管理コンソール) にある操作名が同じであることを確認する必要があります。 それ以外の場合は、送信ポートを介して SAP システムへのメッセージを送信中にエラーが表示されます。  
  
-   のみ、SAP システムに接続するポートの資格情報を提供する必要があります。 バインド ファイルには、接続に使用するユーザー名を保持は、セキュリティ上の理由、バインド ファイルはパスワードです。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
-   バインド ファイルをインポートするときに、ダイアログ メッセージ通知する、バインド ファイル内の BizTalk アプリケーション名では、バインド ファイルをインポートするアプリケーション名が一致しないことを取得する可能性があります。 安全にこのメッセージは無視して続行できます。  
  
-   バインド ファイルは、受信場所もにポートの名前を格納および構成。 バインド ファイルをインポートする BizTalk アプリケーションは、ポート、または、同じ BizTalk アプリケーションで既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが表示されます。 ポートに一意の名前を指定するか、受信場所にバインド ファイルを手動で編集する必要があります。  
  
-   バインド ファイルには、接続 URI に関する情報も含まれています。 バインド ファイルを同じ BizTalk アプリケーション内の既存の受信場所として同じ受信 URI を持つ受信場所を作成する場合は、エラーが表示されます。 一意の URI を指定するバインド ファイルを手動で編集する必要があります。  
  
-   既定では、ポートのバインド ファイル常の定義を含む双方向のポート (送信または受信)。 BizTalk アプリケーションでこのファイルをインポートするときに、双方向の送信を作成またはポートを受信します。 ただし、受信ポートかを一方向の送信を含むオーケストレーションもある可能性があります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートがリストに表示できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーションで作成した物理ポートは双方向のポートのために発生します。 このような場合は、次の変更を加えるバインド ファイルを編集できます。  
  
    |こちらは|方法|  
    |--------------|-------------|  
    |構成するポートのバインド ファイルを編集するための一方向送信ポート|1.次の例の値を変更する**IsTwoWay**プロパティを**false**です。 最初に、この設定は**true**です。<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br />2.次の抜粋をコメント化します。<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
    |構成するポートのバインド ファイルを編集するには、一方向の受信ポート|1.次の例の値を変更する**IsTwoWay**プロパティを**false**です。 最初に、この設定は**true**です。<br />     `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br />2.次の抜粋をコメント化します。<br />     `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br />     `<SendPipelineData xsi:nil="true" />`<br />     `<SendPipelineData xsi:nil="true" />`|  
  
##  <a name="BKMK_add_wcf_sap"></a>使用して生成されたポートのバインド ファイルを使用して WCF SAP ポートを構成するアダプターを使用する追加のサービス  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]でインポートできるポートのバインド ファイルも作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ポートを作成する、BizTalk WCF SAP で同じポートのバインド ファイルを使用することができます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ただし、WCF SAP ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1.  テキスト エディターで、ポートのバインド ファイルを開きます。  
  
2.  検索して"Wcf-custom"を使用する WCF SAP アダプターを追加した名前に置き換えます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 たとえば、"SAPAdapter"として WCF SAP アダプターを追加した場合は、"SAPAdapter"と"Wcf-custom"を置き換えます。  
  
3.  "ConfigurationClsid"属性を検索し、既存の属性の値を"A5F15999-8879-472d-8C62-3B5EA9406504"に置き換えます。  
  
4.  保存して、バインド ファイルを閉じます。  
  
5.  バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 [SAP アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)手順について説明します。
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)