---
title: "WCF LOB Adapter SDK の WSDL プロキシを使用して名前空間を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc85d47da81d2d7425c7db4aad90ea32389f7d84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK の WSDL プロキシで使用する名前空間
[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] WSDL とプロキシを使用して、開発者によって指定された値を使用してアダプターを生成、 [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] SERVICENAMESPACE プライベート変数の変更を使用してコードで指定されているか、または`Namespace`アダプターのプロパティです。  
  
 内で定義されている要素とスキーマ型、 \<wsdl:types >\<スキーマ > 既定では、{OperationNamespace} を使用します。 特定の種類、オーバーライドされた TypeNamespace 設定がある場合、 **TypeMetadata**オブジェクト、その名前空間は複合型の使用やまたは要素の定義。  
  
## <a name="impact-on-wsdl"></a>WSDL に与える影響  
 次の表では、カスタム アダプターに異なる名前空間が、対応する WSDL に与える影響を示します。 表内の ~ {OperationNamespace} は、URI のクラスの名前空間のマッピングたとえば、{OperationNamespace} は"myscheme://a.b/c"~ {OperationNamespace} myscheme.a.b.c になります。  
  
|WSDL のコンストラクト|構文|  
|--------------------|------------|  
|WSDL の targetNamespace<br /><br /> Xmlns:ts|{Custom}Adapter.Namespace|  
|\<wsdl:portType >|{スキーム}. 最大 {OperationNamespace}|  
|WSDL 入力メッセージ名|{スキーム}. 最大 {OperationNamespace} _ {OperationName} _InputMessage|  
|WSDL の出力メッセージ名|{スキーム}. 最大 {OperationNamespace} _ {OperationName} _OutputMessage|  
|\<wsdl:types >\<スキーマ > targetNamespace|{スキーム}://{OperationNamespace}|  
|\<要素 >\<complexType >|その値が null または空でない場合は、{TypeNamespace} を使用します。|  
  
## <a name="impact-on-proxy"></a>プロキシへの影響  
 名前空間では、プロキシ内の次の 3 つの異なる属性が影響を受けます。  
  
-   [**System.ServiceModel.ServiceContractAttribute**(名前 ="{スキーム}. 最大 {OperationNamespace}"、Namespace="{Custom}Adapter.Namespace"]  
  
-   [**System.ServiceModel.MessageContractAttribute**(WrapperName WrapperNamespace"DivideResponse"= =「{スキーム}://{OperationNamespace}」、IsWrapped = true)]  
  
-   [**System.ServiceModel.MessageBodyMemberAttribute**(Namespace =「{スキーム}://{TypeNamespace}」、順序 = 0)]  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して、開発のベスト プラクティス](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)