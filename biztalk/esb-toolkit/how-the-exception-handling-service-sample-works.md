---
title: 例外処理サービス サンプルのしくみ |Microsoft ドキュメント
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
ms.openlocfilehash: eac3a9ff96025f5248c0434a69c38eb01a704488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22293922"
---
# <a name="how-the-exception-handling-service-sample-works"></a>例外処理サービス サンプルのしくみ
例外処理サービス サンプルは、生成されるサービス プロキシ サービスを処理する例外を含んでいる標準的な .NET Windows フォーム アプリケーションです。 アプリケーションから成る 1 つのボタンと 1 つのフォーム**生成例外**です。 インスタンス、このボタンをクリックすると、 **FaultMessage**クラスが生成されます。 **FaultMessage**クラスは、基に、Web サービス記述言語 (WSDL)、例外処理の Web サービスによって提供される Microsoft Visual Studio によって生成されたクラスです。 このインスタンスのプロパティはプロパティにパラメーターとして渡される前に、外部アプリケーションで発生した障害をシミュレートする既定値が入力されます、 **SubmitFault**例外処理の web メソッドサービス。  
  
 例外処理の Web サービスの動作方法の詳細については、次を参照してください。 [、例外処理 Web Service](../esb-toolkit/the-exception-handling-web-service.md)です。