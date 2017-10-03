---
title: "パイプライン コンポーネントにおける SOAP ヘッダーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
- Web services, SOAP headers
- creating, SOAP headers
ms.assetid: 5b4a8902-e8f5-44a4-88f7-17f47a9deecd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c11b74aafe53150ced42d0c53a2e19a2c5080fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-pipeline-components"></a>パイプライン コンポーネントにおける SOAP ヘッダーの使用
パイプライン コンポーネントでは、SOAP ヘッダー コンテキスト プロパティにアクセスするに使用するコンテキスト プロパティ名とターゲットの名前空間の組み合わせで説明したよう[オーケストレーションの SOAP ヘッダーを使用して](../core/using-soap-headers-in-orchestrations.md)です。  
  
 次のコード例では、要求 SOAP ヘッダーを設定、プロパティ名の送信パイプライン コンポーネントで**OrigDest**:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<?xml version=\"1.0\"?>  
          <OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </OrigDest>";  
inmsg.Context.Write("OrigDest","http://schemas.microsoft.com/BizTalk/2003/SOAPHeader", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。  
  
> [!NOTE]
>  オーケストレーションから Web サービスを使用する (呼び出す) 場合、SOAP アダプタは、パススルー スタイルの受信パイプラインおよび送信パイプラインのみをサポートします。 カスタム パイプラインを使用できますが、メッセージのボディ部を変更するコンポーネントを含めることはできません。 これらのコンポーネントには、XML アセンブラ、XML 逆アセンブラ、および XML 検証の各コンポーネントが含まれます。  
  
## <a name="see-also"></a>参照  
 [既定のパイプライン](../core/default-pipelines.md)   
 [使用する Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md)