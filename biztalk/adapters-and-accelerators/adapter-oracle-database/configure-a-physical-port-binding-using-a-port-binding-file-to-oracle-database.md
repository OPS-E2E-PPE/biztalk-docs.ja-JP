---
title: Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, configuring by using a port binding file
ms.assetid: 154d219e-c6f3-4f70-9ac5-d9345f5260e9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 716688ab3cbc2431c6058fee17f9dae42ca96ded
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214890"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database"></a>Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマ ファイル以外、Oracle データベース アイテムのメタデータを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]もポートのバインド ファイルを生成します。 作成する物理送信ポートまたは受信ポートを BizTalk アプリケーションにこのバインド ファイルをインポートすることができます。 バインド ファイルをインポートする方法の詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。 このバインド ファイルをインポートする場合、手動で作成する物理送信ポートまたは受信ポートをするはありません。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]文字列型のバインド プロパティの値を指定しないと、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインディングのプロパティとその値、バインド ファイルに必要な場合です。  
  
 ポートのバインド ファイルを常に使用するポートを作成すると、双方向の送信を作成または、ポートを受信します。 一方向の送信を作成またはポートを受信する場合は、ことができます、手動で作成する次の手順で説明した[Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。 または、一方向の送信を作成または受信ポートをポートのバインド ファイルを変更するには、このトピックに記載されている回避策を実行することができます。  
  
 によって生成されたバインド ファイルに関して理解しておく必要があります重要な点は次のとおり、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   ファイルは、特定の名前付け規則で作成されます。 を Oracle データベースにメッセージを送信するには、送信操作のメタデータを生成した場合は、WcfSendPort_OracleDBBinding_Custom.bindinginfo.xml は、ファイルの名前です。  
  
     を Oracle データベースからメッセージを受信するには、受信操作のメタデータを生成した場合は、WcfReceivePort_OracleDBBinding_Custom.bindinginfo.xml は、ファイルの名前です。  
  
-   ファイルには、バインド構成、バインドの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づくポート操作に関する情報が含まれています。 ポートを作成するには、このバインド ファイルをインポートするときに、ポートの物理ポートを構成するために必要なすべての関連情報が自動的に設定します。  
  
    > [!IMPORTANT]
    >  既定では、送信ポートのアクションは、メタデータを生成する操作名にマップされます。 たとえば、ACCOUNTACTIVITY テーブルに対する Select 操作のメタデータを生成する場合、ポートでアクションに設定が`<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />`です。 ただし、BizTalk オーケストレーションで作成する論理送信ポートで、操作名はありません、同じです。 (BizTalk オーケストレーション) の論理ポートと物理送信ポート (BizTalk Server 管理コンソール) にある操作名が同じであることを確認する必要があります。 それ以外の場合は、送信ポートを使用して Oracle データベースにメッセージを送信中にエラーが表示されます。  
  
-   のみ、ポート、Oracle データベースに接続するための資格情報を提供する必要があります。 バインド ファイルには、接続に使用するユーザー名を保持は、セキュリティ上の理由、バインド ファイルはパスワードです。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
-   バインド ファイルをインポートするときに、ダイアログ メッセージ通知する、バインド ファイル内の BizTalk アプリケーション名では、バインド ファイルをインポートするアプリケーション名が一致しないことを取得する可能性があります。 安全にこのメッセージは無視して続行できます。  
  
-   バインド ファイルは、受信場所もにポートの名前を格納および構成。 バインド ファイルをインポートする BizTalk アプリケーションは、ポート、または、同じ BizTalk アプリケーションで既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが表示されます。 ポートに一意の名前を指定するか、受信場所にバインド ファイルを手動で編集する必要があります。  
  
-   バインド ファイルには、接続 URI に関する情報も含まれています。 バインド ファイルを同じ BizTalk アプリケーション内の既存の受信場所として同じ受信 URI を持つ受信場所を作成する場合は、エラーが表示されます。 一意の URI を指定するバインド ファイルを手動で編集する必要があります。 ポーリング ID を含む、一意の URI を指定できます。  
  
-   既定では、ポートのバインド ファイル常の定義を含む双方向のポート (送信または受信)。 BizTalk アプリケーションでこのファイルをインポートするときに、双方向の送信を作成またはポートを受信します。 ただし、受信ポートかを一方向の送信を含むオーケストレーションもある可能性があります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートがリストに表示できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーションで作成した物理ポートは双方向のポートのために発生します。 このような場合は、次の変更を加えるバインド ファイルを編集できます。  
  
    |こちらは|方法|  
    |--------------|-------------|  
    |構成するポートのバインド ファイルを編集するための一方向送信ポート|値を変更するのには次の抜粋では、 **IsTwoWay**プロパティを false にします。 これが設定されていた、true に設定します。<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -次の抜粋をコメント化します。<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
    |構成するポートのバインド ファイルを編集するには、一方向の受信ポート|値を変更するのには次の抜粋では、 **IsTwoWay**プロパティを false にします。 これが設定されていた、true に設定します。<br /><br /> `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br /><br /> -次の抜粋をコメント化します。<br /><br /> `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-oracledb-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>使用して生成されたポートのバインド ファイルを使用して Wcf-oracledb ポートを構成するアダプターを使用する追加のサービス  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk Server 管理コンソールでインポート可能なポートのバインド ファイルを作成します。 同じポートのバインド ファイルを使用しても BizTalk Server 管理コンソールで、BizTalk Wcf-oracledb ポートを作成することができます。 ただし、Wcf-oracledb ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1.  テキスト エディターで、ポートのバインド ファイルを開きます。  
  
2.  検索して置き換えます名を使用するには、Wcf-oracledb アダプターが追加されます。"Wcf-custom"[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 たとえば、"OracleDBAdapter"として Wcf-oracledb アダプターを追加した場合は、"OracleDBAdapter"と"Wcf-custom"を置き換えます。  
  
3.  "ConfigurationClsid"属性を検索し、既存の属性の値を"D7127586-E851-412e-8A8A-2428AEDDC219"に置き換えます。  
  
4.  保存して、バインド ファイルを閉じます。  
  
5.  バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 バインド ファイルをインポートする方法については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)