---
title: ThrowDetailedError スイッチを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160bf585d23ad366d04e9b897c66d45ef8be6bda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333189"
---
# <a name="how-to-use-the-throwdetailederror-switch"></a>ThrowDetailedError スイッチを使用する方法
Web クライアントが受け取るジェネリックでエラーが発生する場合**SoapException**します。  
  
 公開済み Web サービスをデバッグするには、公開された Web サービスから返された例外の詳細のレベルを制御するために Web.config ファイルにスイッチを追加できます。  
  
 Web.config ファイルには、アプリケーション設定スイッチが含まれています**ThrowDetailedError**します。 **False**の既定の設定は、 **ThrowDetailedError**します。 設定を変更する場合**True**、サーバー プロキシは、公開された Web サービスをデバッグできるように、Web クライアントに内部例外情報を返します。  
  
 次の XML コードは、 **ThrowDetailedError**スイッチで Web.config ファイルに表示される、 \<appSettings\>ノード。  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  BizTalk Server 情報は返されません、内部例外を Web クライアントに既定ではアプリケーションのコール スタックなどの機密情報が含まれている可能性がありますので。 デバッグするには、後に設定する必要があります、 **ThrowDetailedError**設定**False**します。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスのデバッグ](../core/debugging-published-web-services.md)