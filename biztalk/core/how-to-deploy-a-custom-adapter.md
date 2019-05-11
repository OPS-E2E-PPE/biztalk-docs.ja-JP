---
title: カスタム アダプターを展開する方法 |Microsoft Docs
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
ms.openlocfilehash: e2d04638aef5172eba3bae57a6f0d315fad66162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385300"
---
# <a name="how-to-deploy-a-custom-adapter"></a>カスタム アダプターを展開する方法
完全なアダプターのインストール プロセスは、次の手順で構成されます。  
  
1.  依存関係を確認します。 たとえば、MSMQ アダプターのインストーラーは、アダプター ランタイムに依存しているため、ローカル MSMQ サービスの存在をチェックします。  
  
2.  ローカル ファイル システムを設定します。 これには、インストール フォルダーを作成し、バイナリとサポート ファイルのコピーが含まれます。 フォルダーへのアクセスおよびファイル アクセスのアクセス許可が正しく構成されていることを確認します。  
  
3.  システムのグローバル アセンブリ キャッシュには、マネージ アセンブリをインストールします。  
  
4.  アダプターのレジストリ キーを作成します。  
  
    > [!NOTE]
    >  32 ビット アダプターの場合、BizTalk Server 管理コンソールは、レジストリの hkey_classes_root はカスタム アダプターの構成を取得するのに使用します。  32 ビット アダプターは、64 ビット サーバーにインストールする場合、BizTalk 機能の管理コンソール代わりに hkey_classes_root \wow6432node\ からアダプター構成データをします。  
  
5.  BizTalk Server にアダプターを追加します。 これは、プロパティの昇格を反映するために使用されるプロパティ スキーマの場合と同様のアダプターの BizTalk 管理データベースに新しいエントリを意味します。 この手順では、BizTalk Server 管理コンソールを使用して手動で実行が場合があります。  
  
## <a name="exceptions"></a>例外  
 アダプターのインストーラーを部分的な BizTalk Server のインストールでの依存関係を確認する必要はありません。 たとえば、管理ツールのみのインストール、アダプター インストーラー必要はありませんアダプター ランタイムが使用されていないために、アダプター ランタイムの依存関係を確認します。 方も BizTalk Server ランタイムのみのインストール場所、アダプターのインストーラーは、アダプター デザイン時の依存関係を確認する必要はありません。  
  
 複数の BizTalk Server 環境では、上記の一覧 (BizTalk Server にアダプターを追加する) の最後のステップは最初の BizTalk Server のアダプターのインストールでのみ発生します。 すべての BizTalk Server サービス インスタンス (既定名は、BizTalkMgmtDB) に同じ BizTalk 管理データベースを共有するためです。 同じグループ内の他の BizTalk server にアダプターを追加する場合は、追加の手順が失敗します。  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a>アダプター アセンブリをグローバル アセンブリ キャッシュにインストールします。  
 別のアダプターのインストール パスで複数の BizTalk Server ホスト環境をサポートするには、システムのグローバル アセンブリ キャッシュにアダプターのアセンブリをインストールする必要があります。  
  
 アダプターのインストールと構成は、新しいアダプターのエントリは、BizTalk 管理データベース (既定の名前 BizTalkMgmtDB) の adm_adapter テーブルに作成されます。 このエントリには、実行時とデザイン時の両方の BizTalk Server で使用されるすべての参照情報が含まれています。  
  
 **InBoundAssemblyPath**と**OutboundAssemblyPath**フィールドは、アダプター バイナリの読み込み先を検索する、BizTalk Server ランタイムで使用します。 BizTalk Server グループの 1 つだけの BizTalk 管理データベースがあるため、グループ内のすべての BizTalk server はこの同じ特定の情報を共有する必要があります。 グループ内の別の BizTalk server にアダプターをインストールする場合は、それらのサーバーで同じインストール パスを使用する必要があります。 ローカル インストール パスが BizTalk 管理データベースに格納されているパスと異なる場合は、BizTalk Server では、アダプター バイナリを読み込むことができません。  
  
 常に、アダプターのアセンブリに厳密な名前で署名し、Gacutil.exe を使用して、アダプターのインストール中に、アダプター アセンブリをシステムのグローバル アセンブリ キャッシュに配置します。 おくことを確認、 **InBoundAssemblyPath**と**OutboundAssemblyPath**フィールドを null または空です。  
  
## <a name="using-the-framework-for-adapter-configuration"></a>アダプター構成のフレームワークを使用します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプター構成ユーザー インターフェイス (UI) プロパティ シートを生成するためのメカニズムを提供します。 構成のプロパティの XML スキーマ定義 (XSD) 定義に基づいています。 このフレームワークの使用は、アダプター開発者向けの大きな課題を紹介します。 このセクションでは、これらの問題の一部で、有効な回避策をお勧めします。  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a>すべてのキーのプロパティのカスタム プロパティ エディターを検討してください。  
 プロパティ シートにプロパティの上に重要なプロパティの検証を配置することはできません。 フレームワークは、UI の検証規則を定義する XML スキーマ定義 (XSD) の simpleType の制約を使用しようとします。 最大と最小値の単純なルールが適用されますが、正規表現の文字列フィールドの制限がサポートされていません。 また、データは、制限が適用される前に、共通言語ランタイム (CLR) 型に変換されます。 つまり、UI のユーザーで範囲外のエラーではなく、暗号のような型変換エラーがされる場合があります。 すべての検証ロジックは不十分です。  
  
 多くのアダプター開発者が採用しているソリューションでは、そのプロパティ シートの主要なプロパティのカスタム プロパティ エディターを作成します。 場合 (大文字と小文字は多くの場合)、さまざまな相互依存プロパティがあるカスタム プロパティ エディターは、1 つのフィールドに結果を結合できます、ランタイムは後で区切ります。 これは、インターフェイスに必要なは、(ただし、通常は少量) のカスタム コードを取得する唯一の方法です。  
  
 カスタム プロパティ エディターは比較的簡単に記述し、それらを使用する XSD のプロパティの注釈を付けることができます。 プロパティ エディターのエントリ ポイントを公開するアセンブリを参照して、注釈と CLR フォームを表示するにはコーディングしています。 通常のユーザー インターフェイスを記述し、Visual Studio によって提供される従来のインターフェイス生成ツールを使用できます。  
  
 次のコードでは、XSD を使用して、カスタム プロパティ エディターを追加する方法を示します。  
  
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
  
 参照されているコードは次のようになります。  
  
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
  
 管理ランタイムでは、グローバル アセンブリ キャッシュに追加する必要がありますので、XSD で参照されるアセンブリを検索できる必要があります。