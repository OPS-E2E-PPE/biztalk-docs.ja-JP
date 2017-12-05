---
title: "ThrowDetailedError スイッチを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90929015e2d1d0567af0ccc5c51c6aae450d49c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a>ThrowDetailedError スイッチを使用する方法
Web クライアントがジェネリック型を受け取るエラーが発生する場合**SoapException**です。  
  
 公開された Web サービスをデバッグするには、この Web サービスから返される例外の詳細レベルを制御するためのスイッチを Web.config ファイルに追加します。  
  
 Web.config ファイルを含む、アプリケーション設定スイッチ**ThrowDetailedError**です。 **False**の既定の設定は、 **ThrowDetailedError**です。 設定を変更する場合**True**、サーバー プロキシは、公開された Web サービスをデバッグできるように、Web クライアントには、内部例外情報を返します。  
  
 次の XML コードは、 **ThrowDetailedError**スイッチ下にある Web.config ファイルに表示される、 \<appSettings\>ノード。  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  内部例外情報には、アプリケーション呼び出し履歴などの機密性の高い情報が含まれている場合があります。そのため、BizTalk Server は、内部例外情報を Web クライアントに返しません。 設定する必要があります、デバッグ後に、 **ThrowDetailedError**設定**False**です。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスのデバッグ](../core/debugging-published-web-services.md)