---
title: 例外処理サービス サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d095752-e212-42bf-9559-efa14d2ad09c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 254d7a5b5cbf2e431ff7db4309774d8315367e2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400783"
---
# <a name="how-the-exception-handling-service-sample-works"></a>例外処理サービス サンプルのしくみ
例外処理サービス サンプルは、例外処理サービスのサービスが生成されたプロキシを含む標準の .NET Windows フォーム アプリケーションです。 アプリケーションを 1 つのボタンを 1 つのフォームの構成は**生成例外**します。 インスタンス、このボタンをクリックすると、 **FaultMessage**クラスが生成されます。 **FaultMessage**クラスは基に、Web サービス記述言語 (WSDL)、例外処理の Web サービスによって提供される Microsoft Visual Studio によって生成されたクラスです。 このインスタンスのプロパティには、プロパティがパラメーターとして渡される前に、外部のアプリケーションで発生する障害をシミュレートする既定値が設定されます、 **SubmitFault**の例外処理 Web メソッドサービス。  
  
 例外処理の Web サービスの動作方法の詳細については、次を参照してください。 [、例外処理 Web Service](../esb-toolkit/the-exception-handling-web-service.md)します。