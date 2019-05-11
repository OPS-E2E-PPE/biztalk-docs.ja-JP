---
title: Web サービスと Web メソッドの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d93635ce23f4ce8899f3d9f6d95dfca2010ea7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389854"
---
# <a name="creating-web-services-and-web-methods"></a>Web サービスと Web メソッドの作成
Web サービスとしてのスキーマを発行するときに、Web サービスと、BizTalk Web サービス公開ウィザードで Web メソッドの作成を制御します。 Web サービスの説明、Web サービスおよび Web サービス ページに表示されるツリー内の Web メソッドの名前を変更することができます。 追加し、Web サービスと Web メソッドを削除することができます。 ウィザードでは、入力パラメーター名として選択した要求スキーマのルート要素名を使用します。 Web メソッドの戻り値は、応答スキーマを返します。  
  
> [!NOTE]
>  ASP.NET Web クライアントは、in、out、同じ型のパラメーターを組み合わせることで Web メソッドのシグネチャを変更することがあります。 ASP.NET Web クライアント可能性がありますから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)** します。  
  
> [!NOTE]
>  場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void** Web クライアントに情報は返されません。 SOAP アダプタおよびオーケストレーション、Web クライアントにスローされる例外は返されません。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Web サービスの公開されたオーケストレーションの名前付け規則  
 BizTalk Web サービス公開ウィザードでは、Web サービス ページで定義する Web サービスの説明に基づく Web サービス (.asmx) ファイル名を生成します。 次の表では、Web サービスのファイル名の既定値を示します。  
  
|生成された Web サービス|ファイル名|  
|---------------------------|---------------|  
|BizTalkWebService|Visual Studio Web サービス プロジェクトの名前|  
|WebService1|Web サービス (.asmx) ファイル名|  
|WebMethod1|Web メソッド名|  
  
 生成された Web サービスでは、残りのノードの名前が反映されません。  
  
## <a name="see-also"></a>参照  
 [Web サービスとしてのスキーマの公開](../core/publishing-schemas-as-a-web-service.md)   
 [BizTalk Web サービス公開ウィザードを使用してスキーマを Web サービスとして公開する方法](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)