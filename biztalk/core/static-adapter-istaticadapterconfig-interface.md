---
title: 静的アダプターの IStaticAdapterConfig インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 296520f7f879e45657c6559827387239d7e10fe0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392865"
---
# <a name="static-adapter-istaticadapterconfig-interface"></a>静的アダプターの IStaticAdapterConfig インターフェイス
静的デザイン時アダプターを実装する必要があります、 **IStaticAdapterConfig**インターフェイス。 これにより、アダプター メタデータの追加ウィザードと対話し、アダプターからサービス組織や個々 のサービスの説明を取得することができます。 ウィザードでは、 **GetServiceOrganization**と**GetServiceDescription**アダプターと連携するメタデータ情報をプルし、BizTalk に追加する方法のプロジェクトで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
 **GetServiceOrganization**メソッドは、アダプターの公開されているサービスの階層構造を表す XML インスタンス ドキュメントを取得します。 この構造体に表示されるサービス組織ツリーが生成されます、 **インポートするサービス**アダプター メタデータの追加ウィザードのページ。  
  
 インポートするサービスを選択すると、ウィザードは呼び出し、 **GetServiceDescription**メソッドは、追加で選択されたサービスのカテゴリに対応する Web サービス記述言語 (WSDL) ファイルの配列を取得するにはアダプター メタデータのウィザードのツリー。 サービスを表すスキーマは XSD ファイルとして生成され、アダプター メタデータの追加ウィザードの完了後に、BizTalk プロジェクトに追加します。  
  
 ファイル アダプターのサンプル、 **GetServiceOrganization**と**GetServiceDescription**メソッド、 **StaticAdapterManagement**クラスで、AdapterManagement.cs クラス ファイルです。 ウィザードでは、 **GetServiceOrganization**上に表示するツリー構造を取得するメソッド、 **インポートするサービス**ページ。 **GetServicesOrganization**ハードコードされた戻り値の次のコード フラグメントに示すように、AdapterManagement.CategorySchema.xml ファイルの値が使用されます。 アダプター開発者は適切な XML ファイルを返すロジックを追加する必要があります。  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  変更してください、 **GetServiceDescription**のメソッド、 **StaticAdapterManagement**クラスではなく、 **DynamicAdapterManagement**クラスは、最初に表示されますファイルです。  
  
 次のコードは、 **GetServiceDescription** AdapterManagement.cs ファイルのメソッド。 返される WSDL ファイルとしてハード コーディングされたファイル service1.wsdl です。 WSDL ファイルとして表されているスキーマを返します。 `wsdls`パラメーターは、ソースによって読み込まれた XML 内の WSDL 参照に対応する一意の WSDL 参照の配列**GetServicesOrganization**します。 返される WSDL 記述のセットは、ポートの種類とメッセージの種類の BizTalk プロジェクトの生成に使用されます。 ツリーで選択可能な 1 つ以上のスキーマ型があれば、1 つ以上の WSDL ファイルを必要があります。 多くの可能なスキーマと WSDL の選択肢がある場合は、場合は、正しい WSDL ファイルを返すデータベース参照を追加します。  
  
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