---
title: "Web サービスと Web メソッドの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74065489e427ae0612897f1f333e3c8e154a535f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-web-services-and-web-methods"></a>Web サービスと Web メソッドを作成します。
スキーマを Web サービスとして公開すると、BizTalk Web サービス公開ウィザードで Web サービスおよび Web メソッドの作成を制御できます。 [Web サービス] ページに表示されるツリー内で、Web サービスの説明、Web サービス、および Web メソッドの名前を変更できます。 Web サービスと Web メソッドの追加および削除を行うことができます。 ウィザードは、選択した要求スキーマのルート要素名を入力パラメータ名として使用します。 Web メソッドの戻り値は、応答スキーマを返します。  
  
> [!NOTE]
>  ASP.NET Web クライアントは、同じ種類の入力および出力パラメータを組み合わせて、Web メソッドの署名を変更することができます。 ASP.NET Web クライアントはから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)**です。  
  
> [!NOTE]
>  場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void**され、Web クライアントに情報は返されません。 SOAP アダプタおよびオーケストレーションは、スローされた例外を Web クライアントに返しません。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>公開オーケストレーションの Web サービスの名前付け規則  
 BizTalk Web サービス公開ウィザードでは、[Web サービス] ページで定義された Web サービスの説明に基づいて、Web サービス (.asmx) のファイル名が生成されます。 次の表は、Web サービス ファイル名の既定値を示しています。  
  
|生成された Web サービス|ファイル名|  
|---------------------------|---------------|  
|BizTalkWebService|Visual Studio Web サービス プロジェクト名|  
|WebService1|Web サービス (.asmx) ファイル名|  
|WebMethod1|Web メソッド名|  
  
 生成された Web サービスには、残りのノードの名前が反映されません。  
  
## <a name="see-also"></a>参照  
 [Web サービスとしてのスキーマの公開](../core/publishing-schemas-as-a-web-service.md)   
 [BizTalk Web サービス公開ウィザードを使用してスキーマを Web サービスとして公開する方法](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)