# mysql_sys.x-ps_digest_avg_latency_distribution-

SELECT 
    COUNT(0) AS `cnt`,
    ROUND((`performance_schema`.`events_statements_summary_by_digest`.`AVG_TIMER_WAIT` / 1000000),
            0) AS `avg_us`
FROM
    `performance_schema`.`events_statements_summary_by_digest`
GROUP BY `avg_us`
