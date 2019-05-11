---
title: WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションの開発 |Microsoft Docs
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
ms.openlocfilehash: a50e2f8ad108f056dda89328ae2c680cce708956
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375558"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle EBS のバインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。  
  
 WCF チャネル モデルを使用して、厳密に型指定されたクラスとチャネル モデルが Oracle E-business suite を実行する操作のきめの細かい制御を提供する WCF サービス モデルの公開は、メソッドの使用上の利点の 1 つ。 このコントロールは、ファクトのことで WCF チャネル モデルを直接制御チャネル経由で送信するメッセージの内容から取得されます。  
  
 特定のシナリオでこの追加レベルの制御はパフォーマンスを向上することはできます。 たとえば、WCF チャネル モデルを使用して、テーブルに対する Update 操作を実行するときに選択的に更新できますターゲット行内の列、メッセージを渡すテンプレートの更新からの列を省略することで。 必要な列のみが"nillable = false"、WSDL でします。 によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントで、テーブルのスキーマ内のすべての列を含むテンプレートのレコードの厳密に型指定されたパラメーターを使用します。  
  
 このセクションのトピックでは、操作を実行する方法を説明します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF チャネル モデルを使用しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle E-business Suite アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [Oracle E-business Suite を使用してチャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [WCF チャネル モデルを使用して Oracle E-business Suite でのインターフェイス テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)