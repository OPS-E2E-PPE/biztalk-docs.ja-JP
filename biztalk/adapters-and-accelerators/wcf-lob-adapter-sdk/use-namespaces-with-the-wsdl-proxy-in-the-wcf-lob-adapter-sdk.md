---
title: WCF LOB Adapter SDK の WSDL プロキシを使用した名前空間を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1838ad1a9f611061477397c548daf80ba31ccab8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362707"
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK の WSDL プロキシを使用した名前空間を使用します。
[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] WSDL とプロキシを使用する開発者によって指定された値を使用してアダプターを生成、 [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] SERVICENAMESPACE プライベート変数の変更をコードで指定されているか、または`Namespace`アダプターのプロパティ。  
  
 スキーマの型および要素内で定義された、 \<wsdl:types\>\<スキーマ\>{OperationNamespace} を使用して、既定では。 特定の種類をオーバーライドされた TypeNamespace 設定がある場合、 **TypeMetadata**オブジェクト、その名前空間は、複合型の使用やまたは要素の定義。  
  
## <a name="impact-on-wsdl"></a>WSDL への影響  
 次の表では、カスタム アダプターで異なる名前空間が対応する WSDL に与える影響を示します。 表に、~ {OperationNamespace} は、URI でのクラスの名前空間のマッピングたとえば、{OperationNamespace} は、"myscheme://a.b/c"~ {OperationNamespace} myscheme.a.b.c になります。  
  
|WSDL のコンストラクト|構文|  
|--------------------|------------|  
|WSDL の targetNamespace<br /><br /> Xmlns:ts|{Custom}Adapter.Namespace|  
|\<wsdl:portType\>|{スキーム} ~ {OperationNamespace}。|  
|WSDL 入力メッセージ名|{スキーム} ~ {OperationNamespace} _ {OperationName} _InputMessage。|  
|WSDL の出力メッセージ名|{スキーム} ~ {OperationNamespace} _ {OperationName} _OutputMessage。|  
|\<wsdl:types\>\<スキーマ\>targetNamespace|{scheme}://{OperationNamespace}|  
|\<element\>\<complexType\>|その値が null または空でない場合は、{TypeNamespace} を使用します。|  
  
## <a name="impact-on-proxy"></a>プロキシへの影響  
 プロキシ内の 3 つの異なる属性は、名前空間の影響を受けます。  
  
-   [**System.ServiceModel.ServiceContractAttribute**(名前 ="{スキーム} ~ {OperationNamespace}"、Namespace="{Custom}Adapter.Namespace"]。  
  
-   [**System.ServiceModel.MessageContractAttribute**(WrapperName="DivideResponse", WrapperNamespace="{scheme}://{OperationNamespace}", IsWrapped=true)]  
  
-   [**System.ServiceModel.MessageBodyMemberAttribute**(Namespace="{scheme}://{TypeNamespace}", Order=0)]  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して開発のベスト プラクティス](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)