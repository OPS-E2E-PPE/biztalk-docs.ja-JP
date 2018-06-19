---
title: カスタム アダプターを展開する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f17b336c-6232-4889-ab7e-92b83fab0f5f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e36443b99f01688a38e66a4a302ab64bb220092f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250298"
---
# <a name="how-to-deploy-a-custom-adapter"></a>カスタム アダプターを展開する方法
アダプターのインストールは、次の手順で行われます。  
  
1.  依存関係をチェックする。 たとえば、MSMQ アダプター ランタイムはローカル MSMQ サービスに依存するため、MSMQ アダプターのインストーラーはローカル MSMQ サービスが存在するかどうかをチェックします。  
  
2.  ローカル ファイル システムを設定する。 この設定作業には、インストール フォルダーの作成と、バイナリ ファイルおよびサポート ファイルのコピーが含まれます。 フォルダーにアクセス可能で、ファイル アクセス許可が適切に構成されていることを確認してください。  
  
3.  マネージ アセンブリをシステムのグローバル アセンブリ キャッシュにインストールする。  
  
4.  アダプターのレジストリ キーを作成する。  
  
    > [!NOTE]
    >  32 ビット アダプターの場合、BizTalk Server 管理コンソールではレジストリ内の HKEY_CLASSES_ROOT からカスタム アダプター構成を取得します。  32 ビット アダプターが 64 ビット サーバーにインストールされている場合、BizTalk Server 管理コンソールでは、代わりに HKEY_CLASSES_ROOT\Wow6432Node\ からアダプター構成データを取得します。  
  
5.  アダプターを BizTalk Server に追加する。 BizTalk 管理データベースにアダプターのエントリとプロパティ スキーマのエントリを新しく追加します。プロパティ スキーマは、アダプターによって昇格されるプロパティを反映するため使用されます。 この手順は、BizTalk Server 管理コンソールを使用して手動で行う必要がある場合があります。  
  
## <a name="exceptions"></a>例外  
 BizTalk Server の部分インストールでは、アダプター インストーラーで依存関係のチェックを行う必要がない場合もあります。 たとえば管理ツールのみのインストールの場合、アダプター ランタイムは必要ないため、アダプター インストーラーでアダプター ランタイムの依存関係をチェックする必要はありません。 BizTalk Server ランタイムのみのインストールの場合も同様に、アダプター インストーラーでアダプター デザイン時の依存関係をチェックする必要はありません。  
  
 BizTalk Server が複数存在する環境の場合、上に示した最後の手順 (アダプターを BizTalk Server に追加する) は、最初の BizTalk Server にアダプターをインストールするときだけ実行します。 この理由は、すべての BizTalk Server サービス インスタンスで同じ BizTalk 管理データベース (既定の名前は BizTalkMgmtDB) が共有されるためです。 同じグループ内の他の BizTalk Server にアダプターを追加しようとすると、手順は失敗します。  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a>アダプター アセンブリをグローバル アセンブリ キャッシュにインストールする  
 アダプターのインストール パスが異なる複数の BizTalk Server ホストが存在する環境をサポートするには、アダプター アセンブリをシステムのグローバル アセンブリ キャッシュにインストールする必要があります。  
  
 アダプターのインストールと構成の過程では、BizTalk 管理データベース (既定の名前は BizTalkMgmtDB) の adm_adapter テーブルにアダプターのエントリが新しく作成されます。 このエントリには、BizTalk Server が実行時およびデザイン時の両方で使用するすべての参照情報が含まれます。  
  
 **InBoundAssemblyPath**と**OutboundAssemblyPath**をアダプターのバイナリの読み込み先を調べるには、BizTalk Server ランタイムによりフィールドが使用されます。 BizTalk Server グループ用の BizTalk 管理データベースは 1 つだけなので、グループ内のすべての BizTalk Server で同じデータベースの情報を共有する必要があります。 グループ内の異なる BizTalk Server にアダプターをインストールする場合は、各サーバーで同じインストール パスを使用する必要があります。 ローカルのインストール パスが BizTalk 管理データベースに格納されているパスと異なる場合、BizTalk Server ではアダプターのバイナリを読み込むことができません。  
  
 常に、アダプターのアセンブリに厳密な名前で署名し、Gacutil.exe を使用して、アダプターのインストール中に、アダプター アセンブリをシステムのグローバル アセンブリ キャッシュに格納します。 ままにしておくことを確認してください、 **InBoundAssemblyPath**と**OutboundAssemblyPath**フィールドを null または空です。  
  
## <a name="using-the-framework-for-adapter-configuration"></a>アダプター構成のフレームワークを使用する  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アダプター構成ユーザー インターフェイス (UI) のプロパティ シートを生成できます。 このプロパティ シートは、構成プロパティの XML スキーマ定義 (XSD) が基になります。 このフレームワークを使用する場合、アダプター開発者は多くの難問に直面します。 ここでは、これらの難問を効果的に回避する方法について説明します。  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a>すべての主要プロパティに対し、カスタム プロパティ エディターを使用する  
 プロパティ シートの上位のプロパティに対し、有意義なプロパティ検証を行うことは不可能です。 このフレームワークは、XML スキーマ定義 (XSD) の SimpleType の制約を使用して UI の検証規則を定義しようとします。 このとき、最大値と最小値による単純な規則は適用されますが、文字列フィールドに対する正規表現の制約はサポートされません。 さらに、制約が適用される前に、データは共通言語ランタイム (CLR) 型に変換されます。 これによって、UI のユーザーには範囲外のエラーではなく不明な型変換エラーが表示される場合があります。 全体的に見て、この検証ロジックは不十分です。  
  
 多くのアダプター開発者が採用している解決策は、プロパティ シートの主要なプロパティに対し、カスタム プロパティ エディターを記述するというものです。 よくあるケースとして、相互に依存するプロパティが多くある場合は、カスタム プロパティ エディターを使用することで結果を単一のフィールドに結合できます。このフィールドは、ランタイムによって後で分離できます。 必要な (通常は少量の) カスタム コードをインターフェイスに挿入するには、これが唯一の方法です。  
  
 カスタム プロパティ エディターの記述は比較的簡単です。XSD のプロパティには、カスタム プロパティ エディターを使用することを注釈で示すことができます。 この注釈では、プロパティ エディターのエントリ ポイントを公開するアセンブリへの参照を指定します。この注釈は、CLR フォームを表示するようコード化されます。 これで、標準的なユーザー インターフェイスを記述でき、Visual Studio で提供される従来のインターフェイス生成ツールを使用できます。  
  
 次のコードは、XSD を使用してカスタム プロパティ エディターを追加する方法を示しています。  
  
```  
<xs:element name="queueDetails" type="xs:string" minOccurs="0">  
    <xs:annotation>  
        <xs:appinfo>  
           <baf:designer>  
               <baf:displayname _locID="queueName">Queue Definition</baf:displayname>  
               <baf:description _locID="receiveQueueDesc">Details of MQSeries Server, Queue Manager and Queue from where you want to receive messages.</baf:description>  
               <baf:category _locID="mqsCategory">MQSeries</baf:category>  
               <baf:editor assembly="Microsoft.BizTalk Server.Adapter.MQSAdmin.dll">Microsoft.BizTalk Server.Adapter.MQSAdmin.MQSUITypeEditor</baf:editor>  
            </baf:designer>  
        </xs:appinfo>  
    </xs:annotation>  
</xs:element>  
  
```  
  
 参照されるコードは次のようになります。  
  
```  
public class MQSUITypeEditor : System.Drawing.Design.UITypeEditor  
{  
public override System.Drawing.Design.UITypeEditorEditStyle GetEditStyle  
(System.ComponentModel.ITypeDescriptorContext context)   
{  
return System.Drawing.Design.UITypeEditorEditStyle.Modal;  
}  
public override object EditValue (System.ComponentModel.ITypeDescriptorContext context,  
System.IServiceProvider provider, object value)   
{  
Form qdForm = new QueueDefinitionForm(value);  
IWindowsFormsEditorService service =   
(IWindowsFormsEditorService)provider.GetService(typeof(IWindowsFormsEditorService));  
DialogResult dialogResult = service.ShowDialog(qdForm);  
//…  
}  
}  
class QueueDefinitionForm : System.Windows.Forms.Form   
{  
//  traditional UI code goes here!  
}  
  
```  
  
 管理ランタイムでは XSD で参照されているアセンブリを特定できる必要があります。このため、アセンブリをグローバル アセンブリ キャッシュに追加します。