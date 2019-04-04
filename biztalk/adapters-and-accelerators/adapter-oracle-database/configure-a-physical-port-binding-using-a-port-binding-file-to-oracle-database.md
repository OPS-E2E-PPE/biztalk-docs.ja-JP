---
title: Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドの構成 |Microsoft Docs
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
ms.openlocfilehash: 846c77040527694822381cfd55c805f78d96e69d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001491"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database"></a>Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマ ファイル以外の Oracle データベース アイテムのメタデータを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ポートのバインド ファイルも生成されます。 BizTalk アプリケーションを作成する物理送信ポートまたは受信ポートには、このバインド ファイルをインポートできます。 バインド ファイルをインポートする手順については、[Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)を参照してください。 このバインド ファイルをインポートする場合は、手動で作成する物理送信ポートまたは受信ポートをする必要はありません。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、バインド ファイルに必要な場合。  
  
 ポートのバインド ファイルを常に使用するポートを作成する双方向の送信を作成します。 または、受信ポート。 一方向の送信を作成またはポートを受信する場合は、ことができます、手動で作成する以下の手順で説明されている[、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。 または、ポートのバインド ファイルを作成する一方向の送信または受信ポートを変更するには、このトピックに記載されている回避策を利用できます。  
  
 によって生成されたバインド ファイルに関して理解しておく必要があります重要な点を次に、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   ファイルは、特定の名前付け規則で作成されます。 Oracle データベースにメッセージを送信するには、送信の操作のメタデータを生成した場合、ファイルの名前は WcfSendPort_OracleDBBinding_Custom.bindinginfo.xml にします。  
  
     Oracle データベースからメッセージを受信するには、受信の操作のメタデータを生成した場合、ファイルの名前は WcfReceivePort_OracleDBBinding_Custom.bindinginfo.xml にします。  
  
-   ファイルには、バインド構成、バインディングの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づき、ポートのアクションに関する情報が含まれています。 ポートを作成するには、このバインド ファイルをインポートするときに物理ポートを構成するために必要なすべての関連情報がポートで自動的に設定します。  
  
    > [!IMPORTANT]
    >  既定では、送信ポートのアクションは、メタデータを生成する操作名にマップされます。 たとえば、ACCOUNTACTIVITY テーブルに対する Select 操作のメタデータを生成する場合、ポートのアクションに設定されて`<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />`します。 ただし、BizTalk オーケストレーションで作成する論理送信ポートでの操作名が同じになりません。 (BizTalk オーケストレーション) の論理ポートと物理送信ポート (BizTalk Server 管理コンソール) での操作名が同じであることを確認する必要があります。 それ以外の場合は、送信ポートを使用して Oracle データベースにメッセージを送信中にエラーが表示されます。  
  
-   Oracle データベースに接続するポートの資格情報を提供するだけです。 バインド ファイルには、接続先となるユーザー名を保持は、セキュリティ上の理由から、バインド ファイルにが含まれていませんパスワードには。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
-   バインド ファイルをインポートすると、バインド ファイル内の BizTalk アプリケーション名が、バインド ファイルをインポートするアプリケーション名と一致しないことを通知ダイアログ メッセージを取得可能性があります。 安全に、このメッセージは無視し、続行できます。  
  
-   バインド ファイルは、ポートの名前を含むもと受信場所。 バインド ファイルをインポートする BizTalk アプリケーションでは、ポート、または、同じ BizTalk アプリケーションに既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが発生します。 ポートの一意の名前を指定するか、受信場所にバインド ファイルを手動で編集する必要があります。  
  
-   バインド ファイルには、接続 URI に関する情報も含まれています。 バインド ファイルを同じ BizTalk アプリケーション内の既存の受信場所として、同じ受信 URI を持つ受信場所を作成した場合は、エラーが発生します。 一意の URI を指定するバインド ファイルを手動で編集する必要があります。 ポーリング ID を含む、一意の URI を指定できます。  
  
-   既定では、ポートのバインド ファイル常に定義されています双方向のポート (送信または受信)。 BizTalk アプリケーションでは、このファイルをインポートするときに双方向の送信を作成します。 または、受信ポート。 ただし、受信ポートかを一方向の送信を含むオーケストレーションがある可能性があります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートは、一覧では使用できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーション内に作成する物理ポートは双方向のポートのために発生します。 このような場合は、次の変更をバインド ファイルを編集できます。  
  
    |こちらは|方法|  
    |--------------|-------------|  
    |構成するポートのバインド ファイルを編集するには、一方向送信ポート|次の例での値を変更する**IsTwoWay**プロパティを false にします。 この設定を true に設定します。<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -次の抜粋をコメント化します。<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
    |構成するポートのバインド ファイルを編集するには、一方向の受信ポート|次の例での値を変更する**IsTwoWay**プロパティを false にします。 この設定を true に設定します。<br /><br /> `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br /><br /> -次の抜粋をコメント化します。<br /><br /> `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-oracledb-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>アダプターを使用して、使用して生成されたポートのバインド ファイルを使用して Wcf-oracledb ポートを構成する追加のサービス  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk Server 管理コンソールでインポートできるポートのバインド ファイルを作成します。 同じポートのバインド ファイルを使用して、BizTalk Wcf-oracledb ポートを BizTalk Server 管理コンソールで作成することもできます。 ただし、Wcf-oracledb ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1. ポートのバインド ファイルをテキスト エディターで開きます。  
  
2. 検索し、の Wcf-oracledb アダプターを追加する名前を持つ"Wcf-custom"を置換[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 たとえば、"OracleDBAdapter"として Wcf-oracledb アダプターを追加した場合は、"OracleDBAdapter"と"Wcf-custom"を置き換えます。  
  
3. "ConfigurationClsid"属性を検索し、既存の属性の値を"D7127586-E851-412e-8A8A-2428AEDDC219"に置き換えます。  
  
4. 保存して、バインド ファイルを閉じます。  
  
5. バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 バインド ファイルをインポートする方法については、[Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)を参照してください。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)