---
title: WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99dfa0c69500b86fe086ce0daa81e3ffb62857d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214802"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle EBS バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。  
  
 WCF チャネル モデルを使用して、厳密に型指定されたクラスとモデルが公開する WCF サービス、チャネル モデルに Oracle E-business Suite で実行する操作をより詳細に制御が用意されているメソッドの使用上の利点の 1 つです。 このコントロールは、ファクトのことで、WCF チャネル モデルを直接制御するチャネル経由で送信するメッセージの内容から取得されます。  
  
 特定のシナリオでは、この余分なレベルの制御と役に立つことがあります。 たとえば、WCF チャネル モデルを使用して、テーブルの更新操作を実行するときに、ターゲット行の列をメッセージを渡すテンプレートの更新からの列を省略することでに更新できます選択的にします。 必要な列のみが"nillable = false"、WSDL でします。 によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントは、テーブルのスキーマ内のすべての列を含むテンプレートに対してレコードの厳密に型指定されたパラメーターを使用します。  
  
 このセクションのトピックでの操作を実行する方法を説明する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle E-business Suite アダプターで WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [Oracle E-business Suite を使用して、チャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [WCF チャネル モデルを使用して Oracle E-business suite のインターフェイス テーブルに対して挿入操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを含む SELECT ステートメントを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)