---
title: SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95b54357-b23d-4ed7-8e31-bd60ed3e625f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631914f72287b9fbd48a6695a4edf79e88d28182
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014203"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-use-the-sql-adapter"></a>SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータ スキーマ ファイル以外の SQL Server 成果物を生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ポートのバインド ファイルも生成されます。 BizTalk アプリケーションを作成する物理送信ポートまたは受信ポートには、このバインド ファイルをインポートできます。 バインド ファイルをインポートする手順については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。 このバインド ファイルをインポートする場合は、手動で作成する物理送信ポートまたは受信ポートをする必要はありません。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、バインド ファイルに必要な場合。  
  
 双方向送信ポートを作成し、ポートのバインド ファイルを常に使用するポートを作成するか、一方向の受信ポート。 手順を使用して手動で作成できます一方向の送信ポートを作成する場合は、 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。 または、一方向の送信ポートを作成するポートのバインド ファイルを変更するには、このトピックに記載されている回避策を利用できます。  
  
> [!NOTE]
>  ポートのバインド ファイルの受信操作の作成は常に一方向の受信ポート。 これは、ため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サポートの一方向受信ポートの受信操作ののみ。  
> 
> [!IMPORTANT]
>  使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] WCF SQL ポートを作成することができますを使用してポートのバインド ファイルを作成しません。 ただし、によって生成されたポートのバインド ファイルにいくつかの変更を加える可能性があります、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] WCF SQL ポートの作成に使用します。 詳細については、次を参照してください。[ポートのバインド ファイルが生成を使用して Consume Adapter Service アドインを使用して WCF SQL ポートを構成する](#BKMK_Create_WCF_SQL)します。  
  
 ファイルのバインドに関して理解していることの重要な点を次に、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]が生成されます。  
  
- ファイルは、特定の名前付け規則で作成されます。 送信操作のメタデータを生成した場合は、SQL Server にメッセージを送信するファイルの名前は WcfSendPort_SqlAdapterBinding_Custom.bindinginfo.xml します。  
  
   受信操作のメタデータを生成した場合は、SQL Server からメッセージを受信するファイルの名前は WcfReceivePort_SqlAdapterBinding_Custom.bindinginfo.xml。  
  
- ファイルには、バインド構成、バインディングの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づき、ポートのアクションに関する情報が含まれています。 ポートを作成する BizTalk アプリケーションにこのバインド ファイルをインポートするときに物理ポートを構成するために必要なすべての関連情報がポートで自動的に設定します。  
  
  > [!IMPORTANT]
  >  既定では、送信ポートのアクションは、メタデータを生成する操作名にマップされます。 たとえば、Customer テーブルに対する挿入操作のメタデータを生成する場合、ポートのアクションに設定されて`<Operation Name="Insert" Action="TableOp/Insert/dbo/CustomerTable" />`します。 ただし、BizTalk オーケストレーションで作成する論理送信ポートでの操作名が同じになりません。 論理操作名の送信 (BizTalk オーケストレーション) のポートを物理送信ポートのことを確認する必要があります (で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール) は、同じです。 それ以外の場合は、SQL Server に送信ポートを通じてメッセージを送信中にエラーが表示されます。  
  
- SQL Server に接続するポートの資格情報を提供するだけです。 バインド ファイルには、接続先となるユーザー名を保持は、セキュリティ上の理由から、バインド ファイルは含まれませんパスワード。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
- バインド ファイルをインポートすると、バインド ファイル内の BizTalk アプリケーション名が、バインド ファイルをインポートするアプリケーション名と一致しないことを通知ダイアログ メッセージを取得可能性があります。 安全に、このメッセージは無視し、続行できます。  
  
- バインド ファイルは、ポートの名前を含むもと受信場所。 バインド ファイルをインポートする BizTalk アプリケーションでは、ポート、または、同じ BizTalk アプリケーションに既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが発生します。 ポートの一意の名前を指定するか、受信場所のバインド ファイルを手動で編集する必要があります。  
  
- バインド ファイルには、接続 URI に関する情報も含まれています。 バインド ファイルを同じ BizTalk アプリケーション内の既存の受信場所として、同じ受信 URI を持つ受信場所を作成した場合は、エラーが発生します。 一意の URI を指定するバインド ファイルを手動で編集する必要があります。  
  
- 既定では、送信操作用のポートのバインド ファイルには、双方向送信ポートの定義が常に含まれます。 BizTalk アプリケーションでは、このファイルをインポートするときに、双方向送信ポートを作成します。 ただし、一方向の送信ポートを持つオーケストレーションがあります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートは、一覧では使用できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーション内に作成する物理ポートは双方向のポートのために発生します。 このような場合は、次の変更をバインド ファイルを編集できます。  
  
  |こちらは|方法|  
  |--------------|-------------|  
  |構成するポートのバインド ファイルを編集するには、一方向送信ポート|1.次の例では、値を変更、 **IsTwoWay**プロパティを**false**します。 設定されていた、 **true**します。<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br />2.次の抜粋をコメント化します。<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
  
  > [!IMPORTANT]
  >  ポートのバインド ファイルの受信操作の作成は常に一方向の受信ポート。 これは、ため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サポートの一方向受信ポートの受信操作ののみ。  
  
##  <a name="BKMK_Create_WCF_SQL"></a> 使用を使用して生成されたポートのバインド ファイルを使用して WCF SQL ポートを構成するアダプターのサービスの追加  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]でインポートできるポートのバインド ファイルも作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 同じポートのバインド ファイルを使用してもに、BizTalk WCF SQL ポートを作成することができます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 ただし、WCF SQL ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1. ポートのバインド ファイルをテキスト エディターで開きます。  
  
2. 検索し、使用の WCF-SQL アダプターを追加した名前の"Wcf-custom"を置換[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 たとえば、"SQLAdapter"として WCF-SQL アダプターを追加した場合は、「SQLAdapter」と"Wcf-custom"を置き換えます。  
  
3. "ConfigurationClsid"属性を検索し、既存の属性の値を"59B35D03-6A06-4734-A249-EF561254ECF7"に置き換えます。  
  
4. 保存して、バインド ファイルを閉じます。  
  
5. バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 バインド ファイルをインポートする方法については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)