---
title: "静的アダプターの IStaticAdapterConfig インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8d95ba4a5945cb43e3681055750cdad628759
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="static-adapter-istaticadapterconfig-interface"></a>静的アダプターの IStaticAdapterConfig インターフェイス
静的デザイン時アダプターを実装する必要があります、 **IStaticAdapterConfig**インターフェイスです。 このインターフェイスによって、アダプター メタデータの追加ウィザードが利用可能になり、アダプターからサービス組織や個々のサービスの説明を取得できます。 このウィザードでは、 **GetServiceOrganization**と**GetServiceDescription**アダプターと連携するメタデータ情報を取得し、BizTalk に追加する方法でプロジェクトを[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
 **GetServiceOrganization**メソッドは、アダプターの公開されたサービスの階層構造を表す XML インスタンス ドキュメントを取得します。 この構造体に表示されるサービス組織ツリーが生成されます、 **インポートするサービス**アダプター メタデータの追加ウィザードのページです。  
  
 インポートするサービスを選択すると、ウィザードは呼び出し、 **GetServiceDescription**メソッドの追加 で選択されたサービス カテゴリに対応する Web サービス記述言語 (WSDL) ファイルの配列を取得するにはアダプター メタデータのウィザードのツリーです。 アダプター メタデータの追加ウィザードの完了後、サービスを表すスキーマが XSD ファイルとして生成され、BizTalk プロジェクトに追加されます。  
  
 ファイル アダプター サンプルでは、 **GetServiceOrganization**と**GetServiceDescription**にメソッドが存在する、 **StaticAdapterManagement**クラス内で、AdapterManagement.cs クラス ファイルです。 このウィザードでは、 **GetServiceOrganization**上に表示するツリー構造を取得するメソッド、 **インポートするサービス**ページ。 **GetServicesOrganization**ハードコードされた戻り値の次のコード フラグメントに示すように、AdapterManagement.CategorySchema.xml ファイルの値が使用されます。 アダプター開発者は、適切な XML ファイルを返すためのロジックを追加する必要があります。  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  変更してください、 **GetServiceDescription**のメソッド、 **StaticAdapterManagement**クラスではなく、 **DynamicAdapterManagement**で最初に表示されるクラスファイル。  
  
 次のコードは、 **GetServiceDescription** AdapterManagement.cs ファイルのメソッドです。 ここでは、返される WSDL ファイルとしてファイル service1.wsdl がハードコードされており、 WSDL ファイルとして表されているスキーマが返されます。 `wsdls`パラメーターは、ソースによって読み込まれた XML 内の WSDL 参照に対応する一意の WSDL 参照の配列**GetServicesOrganization**です。 返される WSDL 記述のセットは、BizTalk プロジェクトのポートの種類とメッセージの種類を生成するために使用されます。 ツリー内に選択できるスキーマの種類が複数存在する場合は、複数の WSDL ファイルが必要です。 スキーマと WSDL の選択肢が多くある場合は、正しい WSDL ファイルを返すためデータベース検索を追加することもできます。  
  
```  
/// <summary>     
        /// Get the WSDL file name for the selected WSDL  
        /// </summary>  
        /// <param name="wsdls">place holder</param>  
        /// <returns>An empty string[]</returns>  
        public string[] GetServiceDescription(string[] wsdls)   
      {  
            string[] result = new string[1];  
            result[0] = GetResource("AdapterManagement.service1.wsdl");  
            return result;  
        }  
```  
  
## <a name="see-also"></a>参照  
 [静的デザイン時アダプター構成](../core/static-design-time-adapter-configuration.md)