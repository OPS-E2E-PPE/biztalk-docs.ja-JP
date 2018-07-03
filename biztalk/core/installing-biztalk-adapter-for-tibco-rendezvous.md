---
title: TIBCO Rendezvous アダプターのインストール、スキーマ、および制限事項 |Microsoft Docs
description: インストール、スキーマの生成、および BizTalk Server で TIBCO Rendezvous の BizTalk アダプターの制限事項
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6404e7e-f671-4c57-a222-0bbe7cbc334f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1eafd0c4a5ff96c3083d28b23347a2908aa52c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022104"
---
# <a name="install-schemas-and-limitations-of-the-tibco-rendezvous-adapter"></a>インストール、スキーマ、および、TIBCO Rendezvous アダプターの制限事項

## <a name="install-and-setup"></a>インストールとセットアップ

[インストールし、構成のエンタープライズ アプリケーション アダプター](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)エンタープライズ アダプターをインストールする手順を含み、キーの情報を知ると、アダプターをインストールする前に、アダプターをインストールした後も含まれます。 

## <a name="generate-schemas"></a>スキーマを生成します。
TIBCO Rendezvous システムには、メッセージの種類のリポジトリは含まれていません。 すべてのメッセージの構築と解析は、Rendezvous アプリケーション レベルに組み込まれています。 この制限により、アダプターは、スキーマ生成機能を提供できません。  
  
スキーマを記述して、使用する必要があります**既存項目の追加**Visual Studio でオーケストレーション用にインポートします。 スキーマは、BizTalk Server の開発ツールに必要で、Visual Studio での統合において非常に重要な役割を果たします。 BizTalk Server の開発者は、完全なスキーマを作成する必要はなく、最小限のスキーマやその中間のスキーマも作成できます。  

## <a name="limitations"></a>制限事項

- フィールドの名前の一意性は保証されません。 TIBCO Rendezvous メッセージに 2 つの同じフィールド名がある場合、生成される XML は無効になります。  
  
- フィールドを並べ替えることはできません。  
  
- TIBCO Rendezvous のドキュメントによると、サブジェクト名には印刷できない文字を使用できないことになっていますが、そのような文字を使用することはできます。 BizTalk Adapter for TIBCO Rendezvous では印刷できない文字が入ったサブジェクト名をサポートしていません。  
  
- デーモンへのセキュリティで保護された接続はサポートされていません。  
  
- カスタム データ型はサポートされていません。  
  
- 認定メッセージングは送信側ではサポートされていません。  
- 
  ## <a name="next-step"></a>次の手順

[チュートリアル: Microsoft BizTalk Adapter for TIBCO Rendezvous の使用](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)  