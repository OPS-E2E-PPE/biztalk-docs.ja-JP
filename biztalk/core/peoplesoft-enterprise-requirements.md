---
title: "PeopleSoft Enterprise の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft Enterprise, requirements
- send handlers, PeopleSoft requirements
- CLASSPATH environment variable
- custom component interface object
- system requirements
- GET_CI_INFO.pc
ms.assetid: fabd808d-d9b6-43b0-a12a-727189f00a9d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f267afce09e9c50d732d376fde43beaa1ef39a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-enterprise-requirements"></a>PeopleSoft Enterprise の要件
## <a name="send-handler-peoplesoft-requirements"></a>送信ハンドラー PeopleSoft の要件  
 Microsoft BizTalk Adapter for PeopleSoft Enterprise にはカスタム コンポーネント インターフェイス (CI) が提供されているので、Java API を使用してアクセスすることができます。 PeopleSoft ツールを使用して PeopleSoft システムにカスタム CI オブジェクトの `GET_CI_INFO` を配置し、BizTalk Adapter for PeopleSoft Enterprise に必要なメタデータ情報を提供します。 詳細については、次を参照してください。[を使用して PeopleSoft Enterprise に準備](../core/preparing-to-use-peoplesoft-enterprise.md)です。  
  
 1 回は、カスタム コンポーネント インターフェイスをアップロードします。 この `GET_CI_INFO.pc` ファイルで製品をインストールします。アダプターで CI を参照するには、このファイルがインストールされている必要があります。 PeopleSoft Application Designer にアクセスできる必要がありますが、BizTalk Server コンピューター上に Application Designer アプリケーションが存在している必要はありません。 Application Designer を使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。  
  
 環境変数 CLASSPATH を設定する必要がありますのでから PeopleSoft コンピューターにアクセスする必要があります (情報を設定または、**トランスポートのプロパティ**画面) を PeopleSoft の指す`PSJOA/psjoa.jar`ファイル。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 [計画とアーキテクチャ](../core/planning-and-architecture13.md)